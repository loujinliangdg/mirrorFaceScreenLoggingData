<template>
    <div class="page">
        <div class="row">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="label">基础代谢：</div>
                    <div class="flex1"><input class="input" type="text" :value="healthData.bmr" placeholder="请输入" @input="input($event,'bmr')"></div>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="label">肥胖等级：</div>
                    <div class="flex1">
                        <select name="fatWeightStatusText" id="" placeholder="请选择" v-model="healthData.fatWeightStatusText" @change="selectChange">
                            <option value="较轻">较轻</option>
                            <option value="正常">正常</option>
                            <option value="轻度肥胖">轻度肥胖</option>
                            <option value="中度肥胖">中度肥胖</option>
                            <option value="重度肥胖">重度肥胖</option>
                            <option value="极度肥胖">极度肥胖</option>
                        </select>
                    </div>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="label">健康指数</div>
                    <div class="flex1 flex align-items-center">
                        <div class="flex1">
                            <input class="input" v-model="healthData.healthScore" type="text" placeholder="请输入" @input="input($event,'healthScore')">
                        </div>
                        <div>分</div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">体重：</div>
                        <div class="flex1"><input class="input" v-model="healthData.weight" type="text" placeholder="请输入" @input="input($event,'weight')"></div>
                        <div>kg</div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <select name="weightStatusText" id="" v-model="healthData.weightStatusText" @change="selectChange">
                                <option value="低">低</option>
                                <option value="正常">正常</option>
                                <option value="高">高</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">体脂率：</div>
                        <div class="flex1"><input class="input" v-model="healthData.fatPercentage" type="text" placeholder="请输入" @input="input($event,'fatPercentage')"></div>
                        <div>%</div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <select name="fatPercentageStatusText" id="" v-model="healthData.fatPercentageStatusText" @change="selectChange">
                                <option value="低">低</option>
                                <option value="正常">正常</option>
                                <option value="较高">较高</option>
                                <option value="高">高</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">脂肪：</div>
                        <div class="flex1"><input class="input" v-model="healthData.fatWeight" type="text" placeholder="请输入" @input="input($event,'fatWeight')"></div>
                        <div>kg</div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <div>{{healthData.fatPercentageStatusText}}</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">内脏脂肪：</div>
                        <div class="flex1"><input class="input" v-model="healthData.visceralFatPercentage" type="text" placeholder="请输入" @input="input($event,'visceralFatPercentage')"></div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <select name="visceralFatPercentageStatusText" id="" v-model="healthData.visceralFatPercentageStatusText" @change="selectChange">
                                <option value="正常">正常</option>
                                <option value="超标">超标</option>
                                <option value="高">高</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">蛋白质：</div>
                        <div class="flex1"><input class="input" type="text" v-model="healthData.proteinWeight" placeholder="请输入" @input="input($event,'proteinWeight')"></div>
                        <div>kg</div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <select name="proteinStatusText" id="" v-model="healthData.proteinStatusText" @change="selectChange">
                                <option value="低">低</option>
                                <option value="正常">正常</option>
                                <option value="高">高</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">水分：</div>
                        <div class="flex1"><input class="input" v-model="healthData.waterWeight" type="text" placeholder="请输入" @input="input($event,'waterWeight')"></div>
                        <div>kg</div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <select name="waterStatusText" id="" v-model="healthData.waterStatusText" @change="selectChange">
                                <option value="低">低</option>
                                <option value="正常">正常</option>
                                <option value="高">高</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">肌肉：</div>
                        <div class="flex1"><input class="input" type="text" v-model="healthData.muscleWeight" placeholder="请输入" @input="input($event,'muscleWeight')"></div>
                        <div>kg</div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <select name="muscleStatusText" id="" v-model="healthData.muscleStatusText" @change="selectChange">
                                <option value="低">低</option>
                                <option value="正常">正常</option>
                                <option value="高">高</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">骨骼肌：</div>
                        <div class="flex1"><input class="input" type="text" v-model="healthData.boneMuscleWeight" placeholder="请输入" @input="input($event,'boneMuscleWeight')"></div>
                        <div>kg</div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <select name="boneMuscleStatusText" id="" v-model="healthData.boneMuscleStatusText" @change="selectChange">
                                <option value="低">低</option>
                                <option value="正常">正常</option>
                                <option value="高">高</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row row2">
            <div class="inner">
                <div class="flex align-items-center">
                    <div class="flex1 flex align-items-center">
                        <div class="label">骨质：</div>
                        <div class="flex1"><input class="input" type="text" v-model="healthData.boneWeight" placeholder="请输入" @input="input($event,'boneWeight')"></div>
                        <div>kg</div>
                    </div>
                    <div class="flex1 flex align-items-center">
                        <div class="label">等级：</div>
                        <div class="flex1">
                            <select name="boneStatusText" id="" v-model="healthData.boneStatusText" @change="selectChange">
                                <option value="低">低</option>
                                <option value="正常">正常</option>
                                <option value="高">高</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <a href="javascript:;" class="weui_btn weui_btn_primary" @click="submitData()">{{btnMessage}}</a>
        <div id="toast" v-show="toastShow">
            <div class="weui_mask_transparent"></div>
            <div class="weui_toast a">
                <p class="weui_toast_content">{{alertMsg}}</p>
            </div>
        </div>
    </div>
</template>

<script>
    import req from '../../assets/js/req'
    export default {
        data(){
            return {
                timer:null,
                alertMsg:'',
                toastShow:false,
                btnMessage:'提交',
                userId: "",     //用户id
                healthData: {
                    healthScore: "",   //健康指数
                    bmr: "",    //基础代谢
                    weight: "",   //体重
                    weightStatusText: "",   //体重等级
                    fatWeightStatusText: "",   //肥胖等级
                    fatPercentage: "",    //体脂率
                    fatPercentageStatusText: "",  //体脂率等级
                    fatWeight: "",   //脂肪
                    visceralFatPercentage: "",   //内脏脂肪
                    visceralFatPercentageStatusText: "",   //内脏脂肪等级
                    proteinWeight: "",    //蛋白质
                    proteinStatusText: "",   //蛋白质等级
                    waterWeight: "",    //水分
                    waterStatusText: "",    //水分等级
                    muscleWeight: "",    //肌肉
                    muscleStatusText: "",   //肌肉等级
                    boneMuscleWeight: "",   //骨骼肌
                    boneMuscleStatusText: "",   //骨骼肌等级
                    boneWeight: "",   //骨质
                    boneStatusText: ""   //骨质等级
                }
            }
        },
        methods:{
            toast(alertMsg){
                this.alertMsg = alertMsg;
                this.toastShow = true;
                setTimeout(() =>{
                    this.toastShow = false;
                },750)
            },
            // 体重验证证
            submitData(){
                var newHealthData = {}
                for(let key in this.healthData){
                    let value = this.healthData[key];
                    // 如果有未填的数据则不能提交
                    if(!value){
                        return this.toast('信息未填写完整哦');
                    }
                    // 如果以.结尾则删除此点
                    if(/\.$/.test(value)){
                        value = value.replace(/\.*$/,'');
                    }
                    newHealthData[key] = value;
                }

                let params = {
                    userId:this.userId,
                    healthData:newHealthData
                }

                if(this.btnMessage == '提交'){
                    req.post('新增修改数据',params,(result) =>{
                        if(result.code == 401){
                            return this.$router.replace('/login');
                        }
                        if(result.code == 1){
                            this.toast('提交成功，再次点击按钮即可投屏哦')
                            this.btnMessage = '投屏';
                        }
                        else{
                            this.toast(result.alertMsg)
                        }
                    },(error) =>{
                        this.toast(error.toString())
                    })
                }
                else if(this.btnMessage == '投屏'){
                    // 请求投屏
                    // alert('投屏')
                    req.get('投屏',{userId:this.$route.query.id},(result)=>{
                        if(result.code == 401){
                            return this.$router.replace('/login');
                        }
                        if(result.code == 1){
                            setTimeout(() =>{
                                this.$router.back('/');
                            },750)
                        }
                        this.toast(result.alertMsg);
                    },(error) =>{
                        this.toast(error.toString())
                    })
                }
            },
            // 输入框输入时做限制
            input(event,key){
                var oldValue = event.target.value;
                var a = oldValue.replace(/^[0|\D|\.]*/,'').replace(/[^\d\.]/g,'').replace(/\.{2,}/g,'.');
                if(a){
                    var firstDot = a.indexOf('.');
                    if(firstDot != -1){
                        if(firstDot + 2 >= firstDot){
                            a = a.slice(0,firstDot+2)
                        }
                    }
                }
                this.healthData[key] = event.target.value =  a.toString();
                
                if(this.btnMessage == '投屏'){
                    this.btnMessage = '提交';
                }
            },
            // 下拉框发生变化时 如果是投屏按钮 则变为提交按钮
            selectChange(){
                if(this.btnMessage == '投屏'){
                    this.btnMessage = '提交';
                }
            }
        },
        created(){
            this.userId = this.$route.query.id;

            req.get('获取用户最新数据',{userId:this.userId},(result) =>{
                if(result.code == 401){
                    return this.$router.replace('/login');
                }
                if(result.code == 1){
                    let data = result.data.healthData;
                    this.healthData.healthScore = data.healthScore || '';
                    this.healthData.bmr = data.bmr || '';
                    this.healthData.weight = data.weight || '';
                    this.healthData.weightStatusText = data.weightStatusText || '';
                    this.healthData.fatWeightStatusText = data.fatWeightStatusText || '';
                    this.healthData.fatPercentage = data.fatPercentage || '';
                    this.healthData.fatPercentageStatusText = data.fatPercentageStatusText || '';
                    this.healthData.fatWeight = data.fatWeight || '';
                    this.healthData.visceralFatPercentage = data.visceralFatPercentage || '';
                    this.healthData.visceralFatPercentageStatusText = data.visceralFatPercentageStatusText || '';
                    this.healthData.proteinWeight = data.proteinWeight || '';
                    this.healthData.proteinStatusText = data.proteinStatusText || '';
                    this.healthData.waterWeight = data.waterWeight || '';
                    this.healthData.waterStatusText = data.waterStatusText || '';
                    this.healthData.muscleWeight = data.muscleWeight || '';
                    this.healthData.muscleStatusText = data.muscleStatusText || '';
                    this.healthData.boneMuscleWeight = data.boneMuscleWeight || '';
                    this.healthData.boneMuscleStatusText = data.boneMuscleStatusText || '';
                    this.healthData.boneWeight = data.boneWeight || '';
                    this.healthData.boneStatusText = data.boneStatusText || '';

                    this.btnMessage = '投屏';
                }
            },(error) =>{
                this.toast(error.toString())
            })
        }
    }
</script>

<style scoped>
    .page{
        overflow-y: auto;
        -webkit-overflow-scrolling: touch;
        background: #fff;
    }
    .row{
        width: 100%;
        padding-bottom:15.2%;
        border-bottom:1px solid #d9d9d9;
        position: relative;
    }
    .row > .inner{
        position: absolute;
        left:0;
        right:0;
        bottoM:0;
        top:0;
        padding: 0 4%;
    }
    .row > .inner > .flex{
        height: 100%;
    }
    .row2 > .inner > .flex > .flex1.flex{
        height: 100%;
    }
    .row2 > .inner > .flex > .flex1.flex:first-child{
        padding-right: 5px;
    }
    .row2 > .inner > .flex > .flex1.flex:last-child{
        border-left:1px solid #d9d9d9;
        padding-left: 5px;
    }
    .flex{
        display: flex;
    }
    .flex.align-items-center{
        align-items: center;
    }
    .flex1{
        flex: 1;
    }
    .label{
        width: 75px;
    }

    .input{
        width: 100%;
        height: 30px;
        border:0;
        box-sizing: border-box;
        padding: 0.3em;
        font-size: 14px;
    }
    select{
        width: 100%;
        font-size:14px;
    }
   
    .weui_btn{
        border-radius: 0;
        box-shadow: none;
        margin-top: 40px;
        margin-bottom: 0;
    }
    .weui_label{
        width: 100px;
    }
    .last-weui-cell::after{
        content: " ";
        position: absolute;
        left: 0;
        bottom: 0;
        width: 100%;
        height: 1px;
        border-top: 1px solid #d9d9d9;
        color: #d9d9d9;
        -webkit-transform-origin: 0 0;
        -ms-transform-origin: 0 0;
        transform-origin: 0 0;
        -webkit-transform: scaleY(.5);
        -ms-transform: scaleY(.5);
        transform: scaleY(.5);
        left: 15px;
    }
</style>
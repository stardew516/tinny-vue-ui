<template>
  <div class="edit-group">
    <div class="edit-row">
      <input v-if="tag==='input'" :disabled="disable" class="edit-area"
             :class="{'bd-red': validInfo[0], disabled: disable}"
             v-model="val" :placeholder="placeholderText"
             name="">
      <textarea v-if="tag==='textarea'" :disabled="disable" class="edit-area h60" :class="{'bd-red': validInfo[0], disabled: disable}"
                v-model="val"
                :placeholder="placeholderText" name=""></textarea>
      <span class="limit-len" :class="{btm10: tag==='textarea'}" v-if="maxlength!==99999">{{len}}/{{maxlength}}</span>
    </div>
    <div v-if="visibleError" class="errormsg">{{validInfo[0] && validInfo[0].errormsg}}</div>
  </div>
</template>
<script>
  export default {
    props: {
      // 值
      value: {
        type: [String, Number],
        twoway: true,
        default: ''
      },
      // 类型: input textarea
      tag: {
        type: String,
        default: 'input'
      },
      // 超过字符限制, 是否截断
      clip: {
        type: Boolean,
        default: true
      },
      // placeholder
      placeholderText: {
        type: String,
        default: '请输入'
      },
      // 正则约束规范
      pattern: {
        type: Array,
        default: function () {
          return []
        }
      },
      // 是否是必填
      required: {
        type: Boolean,
        default: true
      },
      // 最大长度 不为空时字数限制字段显示
      maxlength: {
        type: Number,
        default: 99999
      },
      // 是否是不可编辑状态
      disable: {
        type: Boolean,
        default: false
      },
      // 校验完后, 回调
      validCallback: {
        type: Function,
        default: function () {}
      },
      // name属性
      name: {
        type: String,
        default: ''
      },
      // 错误信息——内容不为空
      requiredErrormsg: {
        type: String,
        default: '内容不能为空'
      },
      // 是否显示错误信息
      visibleError: {
        type: Boolean,
        default: true
      },
      // 错误信息——长度超限
      maxlengthErrormsg: {
        type: String,
        default: '长度超过限制'
      }
    },
    data () {
      return {
        isValid: true,
        validInfo: [],
        len: 0,
        val: this.value // value值赋值给val, 这样就不会直接修改父组件的值报错了
      }
    },
    watch: {
      val (val) {
        if (this.maxlength && this.clip && val.length > this.maxlength) {
          this.val = this.val.substr(0, this.maxlength)
          this.$el.getElementsByClassName('edit-area')[0].value = this.val
        }
        this.valid(val)
      },
      validInfo () {
        this.validCallback(this.validInfo, this.name)
      }
    },
    methods: {
      blurValid () {

      },
      valid (val = this.val) {
        this.validInfo = []
        this.len = val.length
        if (!val && this.required) {
          this.validInfo.push({
            key: 'required',
            errormsg: this.requiredErrormsg
          })
          this.validCallback(this.validInfo, this.name)
          return this.validInfo
        }
        if (this.maxlength && this.len > this.maxlength) {
          this.validInfo.push({
            key: 'maxlength',
            errormsg: this.maxlengthErrormsg
          })
          this.validCallback(this.validInfo, this.name)
          return this.validInfo
        }
        /** 正则格式
         * pattern: [{
         * name: '姓名',
         * reg: /^1$/,
         * errormsg: '错误信息'
         * }]
         */
        for (let idx in this.pattern) {
          let regObj = this.pattern[idx]
          let valid = regObj.reg
          let errormsg = regObj.errormsg
          let validResult = true
          let key = regObj.name
          if (typeof valid === 'function') {
            validResult = valid(val)
          } else {
            validResult = valid.test(val)
          }

          if (!validResult) {
            this.validInfo.push({
              key: key,
              errormsg: errormsg
            })
          }
        }
        this.validCallback(this.validInfo, this.name)
        return this.validInfo
      }
    },
    ready () {
      this.len = this.val.length
    }
  }
</script>
<style lang="scss" scoped>
  @import '../static/color.scss';
  .h60 {
    height: 60px!important;
  }
  .edit-row {
    position: relative;
  }
  .edit-group {
    position: relative;
  }
  .edit-area {
    width: 100%;
    height: 32px;
    line-height: 32px;
    outline: 0;
    border: 1px solid $border;
    padding: 5px 10px;
    box-sizing: border-box;
    box-shadow: none;
    -webkit-appearance: none;
  &:focus {
     border-color: $border-active !important;
     outline: none !important;
   }
  }
  .limit-len {
    position: absolute;
    right: 5px;
    bottom: 5px;
    background: $white;
    color: $color9;
    font-size: 12px;
  }
  .errormsg {
    color: $danger;
    font-size: 12px;
    text-align: left;
  }
  .disabled {
    background-color: $disabled;
  }
</style>

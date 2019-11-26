# 1. The-type-of-Input
+ Input 标签有很多的Type。例如：text password date tel number checkbox...
  每种Type对应的UI 显示会有差别，输入的字符长度限制也会不同
  - 例如maxlength的设置
  - 当Type为text时，maxlength是有效的
  - 当Type为number时，maxlength没有效果
    ```javascript
       // 解决： 可以在input中去判断value的长度，去限制字符输入-->  oninput="if(value.length>3) value=value.slice(0,3);"
       <em class="dm3">Landline<em class="cRed8">*</em></em>
       <input type="number" name="front1" maxlen="3" oninput="if(value.length>3) value=value.slice(0,3);"/> - 
       <input type="number" name="LandlinePhoneNo" maxlen="8"/>
    ```
  - 当Type为tel时,maxlength是有效的，但是填入输入框里面的字体大小会缩小
 ### 2. Input UI
 + 当input标签的Type为number时，input框会默认加上上下箭头，需求不需要箭头
 ```css
     // 用css去掉input的箭头
      input::-webkit-outer-spin-button,
      input::-webkit-inner-spin-button {
        -webkit-appearance: none !important;
        margin: 0;
      }
      input[type="number"] {
        -moz-appearance: textfield;
      }
      // 去掉一些默认样式
      input[type="date"] {
        -webkit-appearance: textarea;
      }
      input[type="checkbox"] {
        width: 20px;
        height: 20px;
      }
 ```
    
  

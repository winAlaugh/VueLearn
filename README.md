# VueLearn
mySimpleToDoMVC.html解析

使用allList:[]来存储toDo事项，事项采用{completed：false,content:"具体事项"}的对象来表示
使用this.allList.push({completed:false,content:this.inputString});来添加一项待办事项。通过@keyup.enter="submit"来触发添加操作
使用removeTodo: function (todo) {
      this.allList.splice(this.allList.indexOf(todo), 1)
    },
来删除一项事项。
使用<input type="checkbox" v-model="item.completed">来绑定事项的completed属性。通过点击复选框来设置completed属性为false or true。
通过computed属性的filterList来实现筛选功能
computed:{
		filterList:function(){
		  var selected = this.selected;
		  var list = this.allList;
		  if(selected=="all" || selected==""){
		  return list;
		  }else if(selected=="complete"){
		  return list.filter(function (number) {
                        return number.completed == true
                })
		  }else if(selected=="remain"){
		  return list.filter(function(item){return item.completed==false})
		  }
		}
		}

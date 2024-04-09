# javascript-
### 排序

##### 插入排序111

*原理*  
将第一个元素视为==有序序列==，遍历数组，将之后的元素依次==插入==这个有序序列中      
*实现方式*      
利用两个循环，外层循环将数组元素挨个移动，内层循环对外层循环选中的元素(targ=et)及它后面的元素(temp)进行对比。      
正序:外层循环选中的元素(targ=et) < 后面的元素(temp)


```
//  ==> 正序
function insertionSort(arr){
    for(var i=0,target;target=arr[++i];){
    	for(var j=i,temp;temp=arr[--j];){
    		if(target<temp){
    			arr[j+1] = temp;
    		}else{
    			break;
    		}
    	}
    	arr[j+1] = target;
    }
    return arr;
}
var arr = [123,5,147,198,100,8];
// [5, 8, 100, 123, 147, 198]

// ==> 逆序
function insertionSort(arr){
	for(var i=1;i<arr.length;i++){
		var target = arr[i];
		for(var j=i-1;j>=0;j--){
			var temp = arr[j];
			if(temp<target){
				arr[j+1] = temp;
			}else{
				break;
			}
		}
		arr[j+1] = target;
	}
	return arr;
}
var arr = [123,5,147,198,100,8];
console.log(insertionSort(arr));
// [198, 147, 123, 100, 8, 5]
```
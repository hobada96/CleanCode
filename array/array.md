# 배열로 유연한 컬렉션 생성

펼침 연산자

function removeItem(items,removevable){

​	const updated = [];

​	for(let i=0;i<items.length;i++){

​		if(items[i] = 0 ;i<items.length;i++){

​			if(items[i] !== removable){

​				updated.push(items[i]);

​			}

​		}

​	}

​	return updated;

}



리팩토링을 하면, 

function removeItem(items,removable){

​	const index = items.indexOf(removable);

​	items.splice(index, 1);

​	return items;

}



const books = ['practical vim','moby dick', 'the dark tower'];

const recent = removeItem(books, 'moby dick');

const novels = removeItem(books, 'practical vim');

//const로 할당을 했지만 조작이 가능하다.



function removeItem(items, removable){

​	const index = items.indexOf(removeable);

​	return items.slice(0,index).concat(items.slice(index + 1));

}



function removeItem(items, removable){

​	const index = items.indexOf(removable);

​	return[...items.slice(0,index), ...items.slice(index + 1)];

}
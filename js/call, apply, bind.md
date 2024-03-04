# call, apply, bind
함수 호출 방식과 관계없이 this지정이 가능.

## call()
``` js
  function showName(){
    console.log(this.name);
  }
  const mike = {
    name:"Mike"
  }

  showName.call(mike);// Mike
```
모든 함수에서 사용가능하며, this를 특정값으로 지정할 수 있다.
``` js
  const mike = {
    name:"Mike"
  }

  function update(birthYear, occupation) {
    this.birthYear = birthYear;
    this.occupation = occupation;
  }

  console.lof(mike);//{name:"Mike"}

  update.call(mike, 1999, "singer");

    console.lof(mike);//{name:"Mike", birthYear:1999, occupation:"singer"}
```

## apply()
``` js
//~~~
  console.lof(mike);//{name:"Mike"}

  update.apply(mike, [1999, "singer"]);

    console.lof(mike);//{name:"Mike", birthYear:1999, occupation:"singer"}
```
매개변수 처리방식 제외, call과 완전히 같다. 매개변수를 배열로 받는다.

## bind()
``` js
const mike = {
  name:"Mike",
};

function update(bitrhYear, occupation) {
  this.birthYear = birthYear;
  this.occupation = occupation;
}

const updateMike = update.bind(mike);

updateMike(1980, "police");
console.log(mike);
```

함수의 this 값을 영구히 바꿀 수 있다.
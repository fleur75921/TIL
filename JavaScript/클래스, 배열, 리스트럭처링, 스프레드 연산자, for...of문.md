## 자바스크립트 클래스

클래스는 객체를 만들기 위한 청사진 역할을 한다.

<br>

    const user = {
        name: "Max",
        age: 34,
        greet() {
            console.log("Hello!");
            console.log(this.age);
        }
    }

    user.greet() // Hello\n 34

    class User {
        contstructor(name, age) {
            this.name = name;
            this.age = age;
        }

        greet() {
            console.log("Hello!");
            console.log(this.age);
        }
    }

    const user1 = new User("Max", 34);
    user1.greet(); // Hello\n 34

## 자바스크립트 배열

findIndex와 map 메서드가 빈번하게 사용된다.

<br>

    const hobbies = ["Sports", "Cooking", "Reading"];

    const index = hobbies.findIndex((item) => {
        return item === "Sports";
    });

    console.log(index) // 0 (처음 발견한 인덱스를 리턴)

    const editedHobbies = hobbies.map((item) => ({text: item}));
    console.log(editedHobbies); // 객체로 이루어진 배열(모든 원소에 해당 함수를 적용하여 결과를 리턴)

## 리스트럭처링

배열의 이름을 쓰면서 긴 문장으로 참조하는 대신 리스트럭처링을 쓰면 간단하게 원하는 원소에 이름을 부여할 수 있다.

<br>

    const userNameData = ["Max", "Schwarzmuller"];

    const firstName = userNameData[0];
    const lastName = userNameData[1];

    const [firstName, lastName] = userNameData

    같은 방법으로 객체도 분해할 수 있다.

    const { name: userName, age } = {
        name: "Max",
        age: 34
    }
    // name:과 같이 별칭을 부여하면 해당 이름으로 사용할 수 있다.(대신 원래 이름은 사용하지 못한다.)

## 스프레드 연산자

스프레드 연산자를 사용해서 배열을 쉽게 합칠 수 있다.

<br>

    const hobbies = ["Sports", "Cooking"];
    const newHobbies = ["Reading"];

    const mergedHobbies = [...hobbies, ...newHobbies];
    console.log(mergedHobbies); // ["Sports", "Cooking", "Reading"];

## for ... of문

for...of 문을 사용하면 인덱스를 명시하지 않고 배열의 모든 원소를 가져올 수 있다.

<br>

    const hobbies = ["Sports", "Cooking"];

    for(const hobby of hobbies) {
        console.log(hobby);
    }
    // Sports\n Cooking

___
#Postman HW2
___

* http://162.55.220.72:5005/first

**1. Отправить запрос.**

**2. Статус код 200**

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

**3. Проверить, что в body приходит правильный string**

 pm.test("correct string in the body", function () {
    pm.response.to.have.body("This is the first responce from server!");
}); 

* http://162.55.220.72:5005/user_info_3

**1. Отправить запрос.**
**2. Статус код 200**

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
}); 

**3. Спарсить response body в json.**

let resp = pm.response.json();

**4. Проверить, что name в ответе равно name s request (name вбить руками.)**

pm.test("name in the response is equal to name's request", function () {
        pm.expect(resp.name).to.eql("Asiya");
});

**5. Проверить, что age в ответе равно age s request (age вбить руками.)**

pm.test("age in the response is equal to age's request", function () {
        pm.expect(resp.age).to.eql("32");
});

**6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)**

pm.test("salary in the response is equal to salary's request", function () {
        pm.expect(resp.salary).to.eql(2000);
});

**7. Спарсить request.**

let req = request.data

**8. Проверить, что name в ответе равно name s request (name забрать из request.)**

let req_name = resp.name
pm.test("name in the response is equal to name's request", function () {
        pm.expect(resp.name).to.eql(req_name);
});

**9. Проверить, что age в ответе равно age s request (age забрать из request.)**

let req_age = resp.age
pm.test("age in the response is equal to age's request", function () {
        pm.expect(resp.age).to.eql(req_age);
});

**10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)**

let req_salary = resp.salary
pm.test("salary in the response is equal to salary's request", function () {
        pm.expect(resp.salary).to.eql(req_salary);
});

**11. Вывести в консоль параметр family из response.**

let family_resp =  resp.family 
console.log(family_resp)

**12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)**

let u_salary_check_1_5_year = resp.salary * 4
let u_salary_1_5_year =resp.family.u_salary_1_5_year

* http://162.55.220.72:5005/object_info_3

**1. Отправить запрос.**

**2. Статус код 200**

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

**3. Спарсить response body в json.**

let resp = pm.response.json();
console.log(resp)

**4. Спарсить request.**

let req = pm.request.url.query.toObject()
console.log(req)

**5. Проверить, что name в ответе равно name s request (name забрать из request.)**

pm.test("name in the response is equal to name's request", function () {
        pm.expect(resp.name).to.eql(req.name);
});

**6. Проверить, что age в ответе равно age s request (age забрать из request.)**

pm.test("name in the response is equal to name's request", function () {
        pm.expect(resp.age).to.eql(req.age);
});

**7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)**

pm.test("salary in the response is equal to salary's request", function () {
        pm.expect(resp.salary).to.eql(Number(req.salary));
});

**8. Вывести в консоль параметр family из response.**

console.log(resp.family)

**9. Проверить, что у параметра dog есть параметры name.**

pm.test('the dog parameter has name parameters', function() {
  pm.expect(resp.family.pets.dog).to.have.property('name');
});

**10. Проверить, что у параметра dog есть параметры age.**

pm.test('the dog parameter has age parameters', function() {
  pm.expect(resp.family.pets.dog).to.have.property('age');
});p

**11. Проверить, что параметр name имеет значение Luky.**

pm.test("the name parameter has the value Lucky", function () {
        pm.expect(resp.family.pets.dog.name).to.eql("Luky");
});

**12. Проверить, что параметр age имеет значение 4**

pm.test("the age parameter has a value of 4", function () {
        pm.expect(resp.family.pets.dog.age).to.eql(4);
});

* http://162.55.220.72:5005/object_info_4


**1. Отправить запрос.**

**2. Статус код 200**

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

**3. Спарсить response body в json.**

let resp = pm.response.json();
**4. Спарсить request.**

let req = pm.request.url.query.toObject()
console.log (req.salary)

**5. Проверить, что name в ответе равно name s request (name забрать из request.)**

pm.test("name in the response is equal to name's request", function () {
        pm.expect(resp.name).to.eql(req.name);
});

**6. Проверить, что age в ответе равно age из request (age забрать из request.)**

pm.test("age in the response is equal to age's request", function () {
        pm.expect(resp.age).to.eql(Number(req.age));
});

**7. Вывести в консоль параметр salary из request.**

console.log(req.salary)

**8. Вывести в консоль параметр salary из response.**

console.log(resp.salary)

**9. Вывести в консоль 0-й элемент параметра salary из response.**

console.log(resp.salary[0])

**10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.**

console.log(resp.salary[1])

**11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.**

console.log(resp.salary[2])

**12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)**

pm.test("The 1nd element of the salary parameter is equal to salary*3 from request", function () {
        pm.expect(String(resp.salary[0])).to.eql(element0);
});

**13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)**

let element1 =  req.salary * 2
pm.test("The 1nd element of the salary parameter is equal to salary*3 from request", function () {
        pm.expect(Number(resp.salary[1])).to.eql(element1);
});

**14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)**

let element2 =  req.salary * 3
pm.test("The 2nd element of the salary parameter is equal to salary*3 from request", function () {
        pm.expect(Number(resp.salary[2])).to.eql(element2);
});

**15. Создать в окружении переменную name**

**16. Создать в окружении переменную age**
**17. Создать в окружении переменную salary**
**18. Передать в окружение переменную name**
**19. Передать в окружение переменную age**
**20. Передать в окружение переменную salary**
**21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.**

for (let i = 0; i < resp.length; i++) {
  console.log(resp.salary[i])
}

* http://162.55.220.72:5005/user_info_2

**1. Вставить параметр salary из окружения в request**

**2. Вставить параметр age из окружения в age**

**3. Вставить параметр name из окружения в name**

**4. Отправить запрос.**

**5. Статус код 200**

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

**6. Спарсить response body в json.**

 let resp = pm.response.json();

**7. Спарсить request.**
let req = request.data
**8. Проверить, что json response имеет параметр start_qa_salary**

pm.test("oarametr start_qa_salary", function () {
    pm.expect(resp).to.have.property("start_qa_salary");
});

**9. Проверить, что json response имеет параметр qa_salary_after_6_months**

pm.test("parameter qa_salary_after_6_months", function () {
    pm.expect(resp).to.have.property("qa_salary_after_6_months");
});

**10. Проверить, что json response имеет параметр qa_salary_after_12_months**

pm.test("parameter qa_salary_after_12_months", function () {
    pm.expect(resp).to.have.property("qa_salary_after_12_months");
})

**11. Проверить, что json response имеет параметр qa_salary_after_1.5_year**

pm.test("parameter qa_salary_after_1.5_year", function () {
    pm.expect(resp).to.have.property("qa_salary_after_1.5_year");
})

**12. Проверить, что json response имеет параметр qa_salary_after_3.5_years**

pm.test("parameter qa_salary_after_3.5_years", function () {
    pm.expect(resp).to.have.property("qa_salary_after_3.5_years");
})

**13. Проверить, что json response имеет параметр person**

pm.test("parameter person", function () {
    pm.expect(resp).to.have.property("person");
})

**14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)**

let start = req.salary
pm.test("start_qa_salary=salary", function () {
    pm.expect(resp.start_qa_salary).to.eql(Number(start));
});

**15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)**

pm.test("qa_salary_after_6_months=salary*2", function () {
    pm.expect(resp.qa_salary_after_6_months).to.eql(Number(start*2));
});

**16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)**

pm.test("qa_salary_after_12_months=salary*2.7", function () {
    pm.expect(resp.qa_salary_after_12_months).to.eql(Number(start*2.7));

});

**17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)**

pm.test("qa_salary_after_1.5_year=salary*3.3", function () {
    pm.expect(resp["qa_salary_after_1.5_year"]).to.eql(Number(start*3.3));
});

**18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)**

pm.test("qa_salary_after_3.5_years=salary*3.8", function () {
    pm.expect(resp["qa_salary_after_3.5_years"]).to.eql(Number(start*3.8));
});

**19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)**

pm.test("The 1st element from u_name is equal to salary from request", function () {
    pm.expect(resp.person.u_name[1]).to.eql(Number(req.salary));
});

**20. Проверить, что что параметр u_age равен age из request (age забрать из request.)**

pm.test("the u_age parameter is equal to the age of the request", function () {
    pm.expect(resp.person.u_age).to.eql(Number(req.age));
});

**21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)**

pm.test("u_salary_5_years=salary*4.2", function () {
    pm.expect(resp.person.u_salary_5_years).to.eql(Number(start*4.2)); 
    });

**22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.**

 let obj = resp.person;

for (let key in obj) {console.log (key, ':', obj[key])}

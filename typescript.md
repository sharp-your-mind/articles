注意大写首字母
```
type Person = {
    name:string
}

interface Person {
    name:string
    age:number
    location:string
}

interface Chinese extends Person{
    ChineseIdentifyId:string
}
type keys = keyof Chinese
type Man = {
   [key in keys] : Person[key]
}

type ChineseMan = Pick<Chinese,"name"|"age">
type ChineseWoMan = Omit<Chinese,"name"|"age">
```

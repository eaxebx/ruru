# 常量

```rust
const ONE_DAY_SECONDS: u32 = 60 * 60 * 24;
```

# 变量 不可变 隐藏

```rust
let mut x: i32 = 3;
println!("{x}");
x = 6;
println!("{x}");
```

# 变量隐藏

```rust
let spaces = "      ";
let spaces = spaces.len();
println!("{spaces}")
```

# 数据类型

## 整形 浮点型 布尔型 字符型 元组 数组

```rust
let a:i32 = 98_222;
let b:u8 = 0xff;
let c:isize = 0o33;
let d:usize = 0b1111_0000;
let e:u8 = b'A';
let f:f32 = 3.14;
let g:f64 = 3.1415;
let h:bool = false;
let i:char = 'z';

let tup:(i32, f64, u8) = (500, 6.4, 1);
let (x, y, z) = tup;
let j = tup.0;
let k = tup.1;

let m: [i32; 5] = [1,2,3,4,5];
let first = m[0];
```

# 函数

## 如果函数的最后是表达式,那它就是返回值,不写分号

```rust
pub fn test(a:i32)->i32{
    a + 3
}
```

# if 语句

```rust
let x = if a>0 {1} else {2};
    if x == 1 {
        print!("haha")
    } else if x == 2 {
        print!("hehe")
    } else {
        print!("heihei")
    }
```

# loop 循环 没有条件的while

```rust
let mut counter = 0;
    let result = loop {
        counter += 1;
        if counter == 10 {
            break counter * 2;
        }
    };
```

## 标签

```rust
fn main() {
    let mut count = 0;
    'counting_up: loop {
        println!("count = {count}");
        let mut remaining = 10;

        loop {
            println!("remaining = {remaining}");
            if remaining == 9 {
                break;
            }
            if count == 2 {
                break 'counting_up;
            }
            remaining -= 1;
        }

        count += 1;
    }
    println!("End count = {count}");
}
```

# while 循环

```rust
let mut number = 3;

    while number != 0 {
        println!("{number}!");

        number -= 1;
    }
```

# for 循环

```rust
let a = [10, 20, 30, 40, 50];

    for element in a {
        println!("the value is: {element}");
    }


for number in (1..4).rev() {
        println!("{number}!");
    }
    println!("LIFTOFF!!!");
```

# 所有权

## 在函数中使用引用避免所有权转移

```rust
fn main() {
    let s = String::from("lklklkj");
    let len = calc(&s);
    println!("{len}");
}

fn calc(s: &String)->usize {
    s.len()
}
```

## 可变引用

```rust
fn main() {
    let mut s = String::from("hello");

    change(&mut s);
}

fn change(some_string: &mut String) {
    some_string.push_str(", world");
}
```

## slice


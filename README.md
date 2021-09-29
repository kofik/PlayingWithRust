# PlayingWithRust
Basics of Rust programming language

#Install Rust

```shell
Installing rustup on Linux or macOS
rustup is an installer for the systems programming language Rust
curl https://sh.rustup.rs -sSf | sh
or
git clone https://github.com/rust-lang/rust.git
cd rust
cp config.toml.example config.toml
./x.py build && ./x.py install
./x.py install cargo 
    

//or set the build.extended key in 
config.toml to true
```

# Introduction
Rust is a low level or a C like programming language for hardware and easy to use as a scripting language
It can be easily use like node Expressjs or Python Flask with a high performance and less memory use.
It combines power and simplicity in its eco-system.
Fast Easy Flexible and Reliable are ways and love for Rust.

The Rust programming language has gained a lot of attention from the community,
ranking it as the most loved programming language on [StackOverflow](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-languages) developer survey each year since 2016 to 2020.

In order to increase our fluency in Rust, we must read a lot of it. 
We’ll try to go through as many Rust snippets as we can, and explain what 
the keywords and symbols they contain mean.


First of all lets introduce a quick list of testing tools.
They will be useful as long as we go far 


##Creating a project 

```shell
cargo new my_app
```

Navigate to the newly created directory and list its content: you should see two files:

```shell
tree 
.
├── Cargo.toml
└── src
 └── main.rs
```


#Let introduces a variables:
```rust
let x;  
x = 12;  
<==>
let x = 12;
or
let x: i128 = 12;
```

It has 
##Scalar Types:
    signed   integers: i8, i16, i32, i64, i128 and isize (pointer size)
    unsigned integers: u8, u16, u32, u64, u128 and usize (pointer size)
    floating point: f32, f64
    char Unicode scalar values like 'a', 'α' and '∞' (4 bytes each)
    bool
    
##Compound Types
    arrays like [a, b, c,g]
    tuples like (1, true)


##Custom Types:
struct: define a structure 
    Tuple structs, which are, basically, named tuples.
    The classic C structs
    Unit structs, which are field-less, are useful for generics.

##enum: define an enumeration


Names that start with an underscore are regular names, it’s just that the 
compiler won’t warn about them being unused:



##Cargo
Cargo is Rust’s build system and package manager.
Like npm or yarn in Javascript or 
Maven/Gradle for Java developers is use for installing, creating, building, running Rust applications

Dependencies
```shell
apt install g++ python make cmake curl git
```

install these on nightly or beta even if you plan to use stable
```shell
cargo install racer
cargo install rustfmt-nightly
cargo install rustsym
```

## Rustup
Enable you to easily switch between stable, beta, and nightly compilers and keep them updated. 
It makes cross-compiling simpler with binary builds of the standard library for common platforms.

Update Rustup and install the nightly toolchain~
```shell
rustup self update
rustup update nightly
```

Make sure to install all of these components on the same toolchain even 
if its different from the chain you plan to use
```shell
rustup component add rls-preview --toolchain nightly
rustup component add rust-analysis --toolchain nightly
rustup component add rust-src --toolchain nightly
```
 
create an enviroment variable for your rust-src folder
RUST_SRC_PATH: "%USERPROFILE%\.rustup\toolchains\stable-x86_64-pc-windows-msvc\lib\rustlib\src\rust\src"
 
link your rust-src folder to VS code/Src folder~
mklink /D "C:\Program Files\Microsoft VS Code\src" "%USERPROFILE%\.rustup\toolchains\stable-x86_64-pc-windows-msvc\lib\rustlib\src\rust\src"

setup a enviroment variable/set your path so that VSCodium can find the libraries
Linux: LD_LIBRARY_PATH=$(rustc --print sysroot)/lib:$LD_LIBRARY_PATH
Mac: DYLD_LIBRARY_PATH=$(rustc --print sysroot)/lib:$DYLD_LIBRARY_PATH
Windows: "%USERPROFILE%\.rustup\toolchains\lib\rustlib\nightly-x86_64-pc-windows-msvc\lib\"


##SoapUI
is a tool for functional testing, mainly of web services like SOAP based web services and 
RESTful web services, but also HTTP based services and JMS Services as well as databases.

##SOAtest

Advanced REST client allows you to test your APIs

Chrome → Postman is not a framework and is not a library, it is a simple plugin for Chrome browser

##Firefox → REST Easy

##Retrofit 
is a well-known library for networking among Android developers

##Fiddler 
is a Web Debugging Proxy which logs all HTTP(S) traffic between your computer and the Internet. 
Fiddler allows you to inspect all HTTP(S) traffic, set breakpoints, and "fiddle" with 
incoming or outgoing data. Fiddler includes a powerful event-based scripting subsystem, 
and can be extended using any .NET language.

##REST Assured 
is most common Java library for REST api test automation

```java
@Test
public void getCorrectData() {
    given.get("https://jsonplaceholder.typicode.com/users/1")
            .then()
            .statusCode(200)
            .and()
            .assertThat()
            .body("name", equalTo("Kofi Barra"))
            .body("username", equalTo("kofik"))
            .body("email", equalTo("info@web.techy"));
}
```

##Spring REST Template 
is a great library with which you can create a REST client

```java
@Test
public void getCorrectData() {
    RestTemplate restTemplate = new RestTemplate();
    HttpHeaders httpHeaders = new HttpHeaders();
    httpHeaders.setContentType(MediaType.APPLICATION_JSON);
    httpHeaders.add("User-Agent", "chrome");
    HttpEntity httpEntity = new HttpEntity(httpHeaders);
    ResponseEntity<String> responseEntity = restTemplate.exchange("https://jsonplaceholder.typicode.com/users/1",   GET, httpEntity, String.class);
    assertThat(responseEntity.getStatusCode(), equalTo(HttpStatus.OK));
}
```

##Actix-web 
is a simple, pragmatic, extremely fast, web framework for Rust. 
[Actix web site] (https://actix.rs/docs/
https://github.com/actix/examples/tree/master/)
287 Contributors

[Benchmark] (https://www.techempower.com/benchmarks/#section=data-r18)
Known to be use by MSN
Seems to be the best and mature framework for I/O

[Axum] (https://tokio.rs/blog/2021-07-announcing-axum) 
Announced the 07/30/2021 is a new born framework with code beauty in mind and modularity.
Seems to be rolling to all growing fastly and starred since it's born.
It uses Askama the over loved Jinga2 not for Pythonist but for Rustaceans

Every language has something like this. C++ has CAF, Scala has Akka, C# has Orleans.

[Juniper] (https://github.com/graphql-rust/juniper
https://www.youtube.com/watch?v=QXJ0wKBLt-8)
is a GraphQL server library for Rust

[A runtime] for writing reliable asynchronous applications with Rust. Provides I/O, networking, scheduling, timers, ...
(https://tokio.rs)
510 Contributors

[Rocket] is a web framework for nightly with a focus on ease-of-use, expressibility, and speed. 
(https://rocket.rs/guide/)
225 Contributors
Not yet a stable version
Must be with version 0.5 to be release
Not yet asynchronous


[Gotham] flexible web framework that promotes stability, safety, security and speed. 
(https://gotham.rs/)
54 Contributors



##Rust Editors

Launch VSCodium Quick Open (Ctrl+P), paste the following command, and press enter.
```shell
codium install rust-lang.rust
or
codium  install vscode-rust
```

Rust language support in Atom
Install the package language-rust in Atom (Preferences->Packages) or Atom's package manager from a shell:
```shell
apm install language-rust
```

Vim8 packages:
```shell
git clone https://github.com/rust-lang/rust.vim ~/.vim/pack/plugins/start/rust.vim
Pathogen:
git clone --depth=1 https://github.com/rust-lang/rust.vim.git ~/.vim/bundle/rust.vim
vim-plug:
Add Plug 'rust-lang/rust.vim' to ~/.vimrc
:PlugInstall or $ vim +PlugInstall +qall
dein.vim:
Add call dein#add('rust-lang/rust.vim') to ~/.vimrc
:call dein#install()
NeoBundle:
Add NeoBundle 'rust-lang/rust.vim' to ~/.vimrc
Re-open vim or execute :
source ~/.vimrc
```


#Clippy requiring a nightly compiler.

```
shell
rustup install nightly
rustup default nightly
```

We will need Rust Language Server to provide the code completion.
```shell
rustup component add rls-preview --toolchain nightly
rustup component add rust-analysis --toolchain nightly
rustup component add rust-src --toolchain nightly
```
    
For a more wholesome experience, please have some tools as well:

cargo install clippy rustfmt rustsym
For the VSCode press 
cmd-p 
and 
codium install vscode-rust

In VSCodium go to Settings using cmd-, and put the following config elements there:

```javascript    
{
    "rust.cargoPath": "/home/kofik/.cargo/bin/cargo",
    "rust.cargoHomePath": "/home/kofik/.cargo",
    "rust.rustfmtPath": "/home/kofik/.cargo/bin/rustfmt",
    "rust.rustsymPath": "/home/kofik/.cargo/bin/rustsym",
    "rust.rustLangSrcPath": "/home/kofik/.rustup/toolchains/nightly-x86_64-apple-darwin/lib/rustlib/src/rust/src",
    "rust.mode": "rls",
    "rust.rls": {
        "executable": "/home/kofik/.cargo/bin/rls",
        "useRustfmt": true
    }
}
```


##Frameworks

#High-Level Server Frameworks
actix-web  	 Base framework tokio
rocket	 Base framework hyper
warp    Base framework hyper
iron    Base framework hyper

#Low-Level Frameworks
hyper

##Frontend Frameworks
tauri
seed
yew




## Database connection:
    
##[Diesel](http://diesel.rs)
It is a safe, extensible ORM and Query Builder for Rust
231 Contributors

    
```shell
cargo install diesel_cli --no-default-features --features postgres
echo DATABASE_URL=postgres://username:password@localhost/diesel_demo > .env
disel setup
diesel migration generate create blog
diesel migration run
diesel migration redo
```
 
```sql
//vim up.sql
    
CREATE TABLE posts (
  id SERIAL PRIMARY KEY,
  title VARCHAR NOT NULL,
  body TEXT NOT NULL,
  created_at DATE, 
  updated_at CURRENT_DATE,
  published BOOLEAN NOT NULL DEFAULT 'f'
)

    
// vim down.sql
DROP TABLE posts
```


```toml
[dependencies]
diesel = { version = "1.4.8", features = ["<postgres|mysql|sqlite>"] }
dotenv = "0.15.0"
```

Sqlx
is an SQL Toolkit for async, pure Rust SQL crate featuring compile-time checked queries without a DSL. 
Supports PostgreSQL, MySQL, SQLite, and MSSQL. 
It's not an ORM

```rust
use sqlx::postgres::PgPoolOptions;
// use sqlx::mysql::MySqlPoolOptions;

#[async_std::main]
async fn main() -> Result<(), sqlx::Error> {
  
    let pool = PgPoolOptions::new()
        .max_connections(5)
        .connect("postgres://postgres:password@localhost/test").await?;

    // Make a simple query to return the given parameter (use a question mark `?` instead of `$1` for MySQL)
    let row: (i64,) = sqlx::query_as("SELECT $1")
        .bind(150_i64)
        .fetch_one(&pool).await?;

    assert_eq!(row.0, 150);

    Ok(())
}
```

Postgres MySql and Sqlite are supported

Finaly a place that help you building  your [docs](https://dillinger.io/) and [here](http://githubs.blogspot.com/)



##License
    
To be defined 




Happy coding !
    
    

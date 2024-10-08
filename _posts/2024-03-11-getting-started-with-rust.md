---
layout: post
title: Getting Started With Rust
subtitle: Documenting My Rust Learning Journey
cover-img: /assets/img/rust.jpg
share-img: /assets/img/rust.jpg
tags: [rust]
author: M.L De Veer
---

<p align="justify">I came across rust during my national service. My curiosity was sparked when told about its memory management capabilities, which i thought was nothing unique when it comes to programming languages. Example, C-Sharp has similar capabilities with garbage collection. But i was wrong. What makes rust really unique is its concept of ownership and borrowing, a topic i'll write more on later. Initially i had plans of learning Javascript as my second language from C-Sharp but Rust captured my attention, especially with the fact that it is used extensively in embedded systems, an area i wish to transition to when i become an intermediate developer. Another great thing about rust is the available resources for learning, they are free, easily accessible and regularly updated by its robust developer community. One of the best advice i have seen to aid learning is to document it, so that is exactly what i am doing with this post and the subsequent ones to come.</p>

## Table Of Content

- [Installing Rust](#installing-rust)
    - [Installing on Windows](#installing-rust-windows)
    - [Installing on MacOs or Linux](#installing-rust-macos-or-linux)
- [Hello World](#helloworld)
- [Cargo](#cargo)
    - [Creating Projects with Cargo](#cargo-project)
- [Learning Resources](#learning-resources)


<a href="installing-rust"></a>
## Installing Rust


<p align="justify">So let's set up our development environment. I am going to assume anyone reading this already has an ide (integrated development environment) they use. If not then download one. Personally I use vscode and you can download it <a href="https://code.visualstudio.com/download" target="_blank">here</a>.</p>


<a href="installing-rust-windows"></a>
### Installing on Windows

<p align="justify">To install rust on windows, visit the rust website <a href="https://www.rust-lang.org/tools/install" target="_blank">here</a> and download the rustup installer. You don't have to do much, just run the file you downloaded and everything will be setup. You can then check if you've successfully installed it by running the following command in cmd or powershell:</p>


```
rustc --version
```

you should get the following result:

```
rustc x.xx.x (xxxxxxxx 20xx-0x-0x)
```

<p align="justify">where the x's denote the the version number, commit hash, and commit date for the latest stable version of what you've installed.If you see this then you've successfully installed rust. If not, find installed the folders and add the bin folder to your PATH user variable, it should look something like this:</p>


```
C:\Users\username\.cargo\bin
```


<p align="justify">if you do not know how to add files or folders to path i suggest checking <a href="https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/" target="_blank">this article</a> or searching how to. Whichever helps.</p>


<a href="installing-rust-macos-or-linux"></a>
### Installing on MacOS or Linux


<p align="justify">This also applies if you want to install it using the Windows Subsystem for Linux. Open a terminal and run the following command:</p>


```
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

<p align="justify">This command downloads a script and starts the installation of the rustup tool, which installs the latest stable version of Rust. You might be prompted for your password. If the install is successful, the following line will appear:</p>

```
Rust is installed now. Great!
```

<p align="justify">According to the rust book (this section is mostly from there, since i do not use any of these OS), a learning resource i use, macOS and linux users have to also install something called a linker if they do not already have one. It is a program that Rust uses to join its compiled outputs into one file. If you get linker errors, you should install a C compiler, which will typically include a linker. A C compiler is also useful because some common Rust packages depend on C code and will need a C compiler. On macOS, you can get a C compiler by running:</p>


```
$ xcode-select --install
```


<p align="justify">Linux users should generally install GCC or Clang, according to their distribution’s documentation. For example, if you use Ubuntu, you can install the <span style="background-color: #d3d3d3">build-essential</span> package.</p>


<p align="justify">you can update rust or uninstall it using the following commands:</p>


```
rustup update
```

and 

```
rustup self uninstall
```

<p align="justify">The rust installation also comes with a copy of its documentation and  you can access it locally using the following command:</p>

```
rustup doc
```


<a href="helloworld"></a>
## Hello World


<p align="justify">Like every other programming language out there, we always start learning with a very simple Hello World! console application. I suggest creating a directory where you store all your project folders. I have one in documents named rust and that's where i store all the projects and exercises i complete from the learning resource i use. So now in your main directory create a folder called hello_world and open it using your ide of choice. Then create a file called main.rs, open the file and enter the following code:</p>


```rust
fn main() {
    println!("Hello World!");
}
```

<p align="justify">To run this simple program, go to your terminal,make sure you are in the right directory. Usually the terminal in the ide is already at the directory already, but if it's not you can use the cd command and the directory path like below:</p> 

```
cd C:\Users\username\Documents\rust\hello_world
```

then run the following command:

```
rustc main.rs
```

doing this generates a main.exe file that we will execute as seen below:

```
 .\main.exe
```

you should get the following result:

```
Hello World!
```

![main.rs](https://maame-deveer.github.io/techhollow/assets/img/mainrs.jpg)


<a href="cargo"></a>
## Cargo

<p align="justify">Javascript has NPM, C-Sharp has Nuget while Rust has Cargo has its package manager. Cargo is not just rust's package manager but its build system too. Rust developers use this tool to manage their Rust projects because Cargo handles a lot of tasks for you, such as building your code, downloading the libraries your code depends on, and building those libraries. Cargo comes installed with Rust if you used the official installers stated in the installation section. You can check if cargo is installed using the command:</p>

```
cargo --version
```

<p align="justify">If you see a version number, you have it! If you see an error, such as command not found, look at the documentation for your method of installation to determine how to install Cargo separately.</p>


<a href="cargo-project"></a>
### Creating Projects with Cargo

<p align="justify">Instead of manually doing things like before, we can use cargo to create our project and the needed files and folders will be generated for us. Using the below command in your terminal or cmd will create a rust project using cargo:</p>

```
cargo new hello_cargo
```

creating a project with cargo will look something like this:
![cargo](https://maame-deveer.github.io/techhollow/assets/img/cargo.png)

<p align="justify">and unlike before where we had to manually create the folder and script, everything is now done by cargo.</p>

![generated files and folders](https://maame-deveer.github.io/techhollow/assets/img/files.png) ![hello world](https://maame-deveer.github.io/techhollow/assets/img/helloworld.png)

and now to build the project with cargo, you use the following command:

```
cargo build
```

<p align="justify">this command also generates an executable file in target/debug/hello_cargo.exe. you can run the executable in the terminal like this:</p>

```
./target/debug/hello_cargo
```

![cargo build](https://maame-deveer.github.io/techhollow//assets/img/cargobuild.jpg)

<p align="justify">instead of using cargo build, we can use another command that will compile our code and run it too, this command is :</p>

```
cargo run
```

![cargo run](https://maame-deveer.github.io/techhollow/assets/img/cargorun.jpg)

<p align="justify">you can read more on cargo and its various commands <a href="https://doc.rust-lang.org/book/ch01-03-hello-cargo.html" target="_blank">here</a>. this is a resource i am using to study and some explanations are from there.</p>


<a href="learning-resources"></a>
## Learning Resources


* <p align="justify"><a href="https://trainingportal.linuxfoundation.org/courses/getting-started-with-rust-lfel1002" target="_blank">Getting Started with Rust by Linux Foundation :</a> This is an introductory course that brushes over the rust programming language, cargo , how to write various programming elements (variables , functions and so on) in rust, example programs and a lab to practice. Its a free course and you get a certificate when you are done. You will need a linux foundation account to access this resource, it is also free. create one <a href="https://lfx.linuxfoundation.org/" target="_blank">here</a>.</p>


* <p align="justify"><a href="https://doc.rust-lang.org/book/" target="_blank">The Rust Book :</a> This is the resource i use to study. It is very detailed, regularly updated and maintained. There is also one that is interactive by having quizzes you can solve in each page but its pretty much the same resource. The interactive one is the one i use and you can access it <a href="https://rust-book.cs.brown.edu/experiment-intro.html" target="_blank">here</a>. There is also another book resource called <a href="https://practice.course.rs/" target="_blank">Rust by Practice</a>, as its name suggests this one focuses on a lot of practical studying , so more code less explanations to read.They are all free and up to date.</p>


* <p align="justify"><a href="https://youtu.be/BpPEoZW5IiY" target="_blank">Rust Programming Complete Course by FreeCodeCamp :</a> We can alway count on FreeCodeCamp to have tutorials on stuff we want to study. This course is 13 hours 59 minutes long and is very detailed. So it's for those who prefer to learn using videos. They also have a shorter one <a href="https://youtu.be/MsocPEZBd-M" target="_blank">Rust For Beginners</a>, which is an hour and 25 minutes long. so use whichever resource you prefer.</p>


<p align="justify">In conclusion, Rust emerges as a powerful and distinctive programming language, finding applications in addressing security and memory challenges, especially within <a href="https://www.securityweek.com/google-contributes-1-million-to-rust-says-it-prevented-hundreds-of-android-vulnerabilities/" target="_blank">Android development</a>. Its versatile nature allows for the creation of a wide array of applications. The many resources available for study underscores the Rust developer community's commitment to making learning rust easy and accessible. I have already reached learning ownership in my studies, i am initiating documenting early in my learning journey, recognizing the importance of capturing insights from the outset. As I embark on my exploration of Rust, I anticipate building exciting projects and encourage others to join this dynamic journey in a language that not only challenges but also inspires innovation.</p>

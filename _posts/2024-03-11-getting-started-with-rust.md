---
layout: post
title: Getting Started With Rust
subtitle: Starting Rust And Setting Up Your Learning Environment
cover-img: /assets/img/rust.jpg
share-img: /assets/img/rust.jpg
tags: [rust]
author: M.L De Veer
---

<div align="justify">I came across rust during my national service. My curiosity was sparked when told about its memory management capabilities, which i thought was nothing unique when it comes to programming languages. Example, C-Sharp has similar capabilities with garbage collection. But i was wrong. What makes rust really unique is the concept of ownership, a topic i'll write more on later. Initially i had plans of learning Javascript as my second language from C-Sharp but Rust captured my attention, especially with the fact that it is used extensively in embedded systems, an area i wish to transition to when i become an intermediate developer. Another great thing about rust is the available resources for learning, they are free, easily accessible and regularly updated by its robust developer community. One of the best advice i have seen to aid learning is to document it, so that is exactly what i am doing with this post and the subsequent ones to come.</div>

## Table Of Content

- [Installing Rust](#installing-rust)
    - [Installing on Windows](#installing-rust-windows)
    - [Installing on MacOs or Linux](#installing-rust-macos-or-linux)
- [Hello World](#helloworld)
- [Cargo](#cargo)
- [Learning Resources](#learning-resources)

<a href="installing-rust"></a>
## Installing Rust

<div align="justify">So let's set up our development environment. I am going to assume anyone reading this already has an ide (integrated development environment) they use. If not then download one. Personally I use vscode and you can download it <a href="https://code.visualstudio.com/download" target="_blank">here</a>.</div>


<a href="installing-rust-windows"></a>
### Installing on Windows

<div align="justify">To install rust on windows, visit the rust website <a href="https://www.rust-lang.org/tools/install" target="_blank">here</a> and download the rustup installer. You don't have to do much, just run the file you downloaded and everything will be setup. You can then check if you've successfully installed it by running the following command in cmd or powershell:</div>

```
rustc --version
```

you should get the following result:

```
rustc x.xx.x (xxxxxxxx 20xx-0x-0x)
```

<div align="justify">where the x's denote the the version number, commit hash, and commit date for the latest stable version of what you've installed.If you see this then you've successfully installed rust. If not, find installed the folders and add the bin folder to your PATH user variable, it should look something like this:</div>

```
C:\Users\username\.cargo\bin
```

<div align="justify">if you do not know how to add files or folders to path i suggest checking <a href="https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/" target="_blank">>this article</a> or searching how to. Whichever helps.</div>


<a href="installing-rust-macos-or-linux"></a>
### Installing on MacOS or Linux

<div align="justify">This also applies if you want to install it using the Windows Subsystem for Linux. Open a terminal and run the following command:</div>

```
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

<div align="justify">This command downloads a script and starts the installation of the rustup tool, which installs the latest stable version of Rust. You might be prompted for your password. If the install is successful, the following line will appear:</div>

```
Rust is installed now. Great!
```

<div align="justify">According to the rust book (this section is mostly from there, since i do not use any of these OS), a learning resource i use, macOS and linux users have to also install something called a linker if they do not already have one. It is a program that Rust uses to join its compiled outputs into one file. If you get linker errors, you should install a C compiler, which will typically include a linker. A C compiler is also useful because some common Rust packages depend on C code and will need a C compiler. On macOS, you can get a C compiler by running:</div>

```
$ xcode-select --install
```

<div align="justify">Linux users should generally install GCC or Clang, according to their distribution’s documentation. For example, if you use Ubuntu, you can install the <span style="background-color: #d3d3d3">build-essential</span> package.</div>
<br>
<div align="justify">you can update rust or uninstall it using the following commands:</div>

```
rustup update
```

and 

```
rustup self uninstall
```

<div align="justify">The rust installation also comes with a copy of its documentation and  you can access it locally using the following command:</div>

```
rustup doc
```

<a href="helloworld"></a>
## Hello World

<a href="cargo"></a>
## Cargo

<a href="learning-resources"></a>
## Learning Resources


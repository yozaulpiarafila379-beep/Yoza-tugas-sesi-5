<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tugas Sesi 5 - Dart OOP</title>

<style>
body {
    font-family: Arial, sans-serif;
    background: #f4f7f6;
    margin: 0;
    padding: 20px;
}

.container {
    max-width: 900px;
    margin: auto;
    background: white;
    padding: 20px;
    border-radius: 10px;
}

h1, h2 {
    color: #2c3e50;
}

pre {
    background: #272822;
    color: #f8f8f2;
    padding: 15px;
    border-radius: 8px;
    overflow-x: auto;
}

.output-img {
    width: 100%;
    max-width: 500px;
    border: 2px solid #ddd;
    border-radius: 8px;
}

.link {
    background: #3498db;
    color: white;
    padding: 8px 12px;
    display: inline-block;
    border-radius: 5px;
    text-decoration: none;
}

.section {
    margin-bottom: 40px;
}
</style>
</head>

<body>
<div class="container">

<h1>Tugas Sesi 5</h1>
<p>
Nama: Kevin <br>
NIM: 251410004 <br>
Kelas: SI2A
</p>

<!-- ================= SLIDE 3 ================= -->
<div class="section">
<h2>Slide 3 - Multiple Inheritance (Mixin)</h2>

<p>Mixin digunakan untuk menggabungkan beberapa fungsi ke dalam satu class.</p>

<pre>
mixin CanFly {
  void fly() {
    print('Can fly!');
  }
}

mixin CanSwim {
  void swim() {
    print('Can swim!');
  }
}

class Bird with CanFly {}
class Duck extends Bird with CanSwim {}

void main() {
  Duck duck = Duck();
  duck.fly();
  duck.swim();
}
</pre>

<p><b>Run di DartPad (Gist):</b></p>
<a class="link" href="#">Link Gist Kamu</a>

</div>

<!-- ================= SLIDE 4 ================= -->
<div class="section">
<h2>Slide 4 - Mixin dengan State</h2>

<p>Mixin juga bisa memiliki state (variabel).</p>

<pre>
mixin CanFly {
  bool _isFlying = false;

  void fly() {
    if (!_isFlying) {
      _isFlying = true;
      print('Started flying!');
    }
  }
}
</pre>

<p><b>Run di DartPad (Gist):</b></p>
<a class="link" href="#">Link Gist Kamu</a>

</div>

<!-- ================= SLIDE 6 ================= -->
<div class="section">
<h2>Slide 6 - Sealed Class (VS Code)</h2>

<p>Sealed class membatasi pewarisan hanya dalam satu file/library.</p>

<pre>
sealed class ApiResponse {}

class Success extends ApiResponse {
  final String message;
  Success(this.message);
}

class Error extends ApiResponse {
  final String errorMessage;
  Error(this.errorMessage);
}
</pre>

<p><b>Output VS Code:</b></p>
<img class="output-img" src="ss-sealed.png" alt="Output Sealed">

</div>

<!-- ================= SLIDE 7 ================= -->
<div class="section">
<h2>Slide 7 - Handle Response</h2>

<pre>
void handleResponse(ApiResponse response) {
  if (response is Success) {
    print("Success: ${response.message}");
  } else if (response is Error) {
    print("Error: ${response.errorMessage}");
  }
}
</pre>

<p><b>Output VS Code:</b></p>
<img class="output-img" src="ss-handle.png">
</div>

<!-- ================= SLIDE 8 ================= -->
<div class="section">
<h2>Slide 8 - Base Class</h2>

<pre>
base class Animal {
  void speak(){}
}
</pre>

<p><b>Output VS Code:</b></p>
<img class="output-img" src="ss-base.png">
</div>

<!-- ================= SLIDE 9 ================= -->
<div class="section">
<h2>Slide 9 - Contoh Base Class</h2>

<pre>
class Dog extends Animal {
  void speak() {
    print("Woof!");
  }
}
</pre>

<p><b>Output VS Code:</b></p>
<img class="output-img" src="ss-dog.png">
</div>

<!-- ================= SLIDE 10 ================= -->
<div class="section">
<h2>Slide 10 - Final Class</h2>

<pre>
final class Settings {
  final String theme;
  final int fontSize;

  Settings({required this.theme, required this.fontSize});

  void showSettings() {
    print("Theme: ${theme}");
  }
}
</pre>

<p><b>Output VS Code:</b></p>
<img class="output-img" src="ss-final.png">
</div>

<!-- ================= BONUS ================= -->
<div class="section">
<h2>Bonus (Slide 19)</h2>

<pre>
base class Repository {
  void create() {}
  void read() {}
  void update() {}
  void delete() {}
}
</pre>

<p><b>Output VS Code:</b></p>
<img class="output-img" src="ss-bonus.png">
</div>

</div>
</body>
</html>


<h1 align="center" style="font-weight: bold;">Quản lí sinh viên UET 💻</h1>

<p align="center">
<a href="#tech">Technologies</a>
<a href="#started">Getting Started</a>
<a href="#routes">API Endpoints</a>
<a href="#colab">Collaborators</a>
<a href="#contribute">Contribute</a> 
</p>


<p align="center">Một project nhỏ khi thực tập tại FamilySoft</p>


<p align="center">
<a href="https://github.com/ngducmiinh/Quanlysinhvien_UET">📱 Visit this Project</a>
</p>

<h2 id="technologies">💻 Technologies</h2>

- Laravel
- Boostrap
- HTML Blade
- Navicat

<h2 id="started">🚀 Getting started</h2>

Đọc và xem qua code những hướng dẫn phía dưới

<h3>Prerequisites</h3>

Những thứ cần có để chạy dự án

- [Laravel](https://laravel.com/)
- [XAMPP](https://www.apachefriends.org/download.html)
- [Navicat hoặc quản lí database khác]
<h3>Cloning</h3>

How to clone your project

```bash
git clone https://github.com/ngducmiinh/Quanlysinhvien_UET.git
```

<h3>Config .env variables</h2>

Sửa file `.env` cho phù hợp với database của bạn

```yaml
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=final
DB_USERNAME=root
DB_PASSWORD=
```

<h3>Starting</h3>

How to start your project

```bash
open your IDE
php artisan serve
```

<h2 id="colab">🤝 Collaborators</h2>

<p>Special thank you for all people that contributed for this project.</p>
<table>
<tr>

<td align="center">
<a href="https://github.com/ngducmiinh">
<img src="https://avatars.githubusercontent.com/u/130099547?v=4" width="100px;" alt="Fernanda Kipper Profile Picture"/><br>
<sub>
<b>Nguyễn Đức Minh</b>
</sub>
</a>
</td>


</tr>
</table>

<h2 id="contribute">📫 Contribute</h2>

Here you will explain how other developers can contribute to your project. For example, explaining how can create their branches, which patterns to follow and how to open an pull request

1. `git clone https://github.com/Fernanda-Kipper/text-editor.git`
2. `git checkout -b feature/NAME`
3. Follow commit patterns
4. Open a Pull Request explaining the problem solved or feature made, if exists, append screenshot of visual modifications and wait for the review!

# Database
- `users`: Chứa danh sách tài khoản giáo viên và sinh viên
    - `name`: Họ và tên
    - `username`: Tài khoản đăng nhập (nếu là sinh viên thì `username` tương đương Mã số sinh viên)
    - `email`: Email liên hệ
    - `password`: Mật khẩu (sẽ mã hóa khi lưu vào database)
    - `role`: Chức vụ (`student`: Sinh viên, `teacher`: Giáo viên)
    - `profile_id`: ID của profile tương ứng, nếu `role` là `student` thì nó sẽ trỏ đến ID tương ứng trong bảng `student_profiles`, nếu `role` là `teacher` sẽ trỏ đến `teacher_profiles`
- `classes`: Chứa danh sách các lớp học
    - `name`: Tên lớp
- `teacher_profiles`: Lưu thông tin tương ứng với user của giáo viên
- `student_profiles`: Lưu thông tin tương ứng với user của sinh viên
    - `dob`: Ngày sinh
    - `code`: Mã số sinh viên
    - `class_id`: Lớp của sinh viên, trỏ đến ID tương ứng trong bảng `classes`
- `subjects`: Lưu thông tin các môn học
    - `name`: Tên môn
    - `code`: Mã môn
    - `semester`: Kỳ học
- `teacher_subject`: Lưu thông tin các giáo viên sẻ đảm nhận dạy môn học nào
    - `teacher_id`: Trỏ đến ID tương ứng trong bảng `teacher_profiles`
    - `subject_id`: Trỏ đến ID tương ứng trong bảng `subjects`
- `scores`: Lưu thông tin điểm của từng sinh viên với từng môn học
    - `student_id`: Trỏ đến ID tương ứng trong bảng `student_profiles`
    - `subject_id`: Trỏ đến ID tương ứng trong bảng `subjects`
    - `tp1`: Điểm thành phần 1
    - `tp2`: Điểm thành phần 2
    - `qt`: Điểm quá trình
    - `ck`: Điểm cuối kì
    - `tk`: Điểm tổng kết
- `request_edit_score`: Lưu các yêu cầu sửa điểm của sinh viên
    - `score_id`: Trỏ đến ID tương ứng trong bảng `scores`
    - `message`: Tin nhắn yêu cầu sửa điểm

# Tài khoản mặc định
- Sinh viên:
    - Tài khoản: `21020698`
    - Mật khẩu: `1`

- Giáo viên:
    - Tài khoản: `gviena`
    - Mật khẩu: `1`

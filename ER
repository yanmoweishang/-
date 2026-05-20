    USERS {
        INT id PK "用户主键ID（自增）"
        VARCHAR username UK "登录用户名（唯一）"
        VARCHAR password "密码哈希（加密存储）"
        VARCHAR role "角色：admin/teacher/student"
        DATETIME create_time "创建时间"
        DATETIME update_time "更新时间"
    }

    STUDENT {
        INT id PK "学生主键ID（自增）"
        VARCHAR student_id UK "学号（业务唯一）"
        VARCHAR name "姓名"
        VARCHAR gender "性别"
        INT age "年龄"
        VARCHAR major "所属专业"
        VARCHAR grade "年级"
        VARCHAR class_name "班级"
        VARCHAR phone "联系电话"
        VARCHAR email "邮箱"
        VARCHAR address "家庭住址"
        DATETIME create_time "创建时间"
        DATETIME update_time "更新时间"
    }

    COURSE {
        INT id PK "课程主键ID（自增）"
        VARCHAR course_code UK "课程编号（唯一）"
        VARCHAR course_name "课程名称"
        VARCHAR teacher "授课教师"
        INT credit "学分"
        INT hours "总学时"
        VARCHAR semester "开课学期"
        VARCHAR course_type "课程类型：必修/选修"
        VARCHAR department "开课院系"
        DATETIME create_time "创建时间"
        DATETIME update_time "更新时间"
    }

    GRADE {
        INT id PK "成绩记录ID（自增）"
        VARCHAR student_id FK "关联 STUDENT.student_id"
        VARCHAR course_code FK "关联 COURSE.course_code"
        VARCHAR course_name "课程名称（冗余展示）"
        DOUBLE score "考试分数"
        VARCHAR semester "考试学期"
        VARCHAR exam_type "考试类型：期中/期末/补考"
        VARCHAR grade_level "成绩等级：优秀/良好/中等/及格/不及格"
        VARCHAR teacher "录入教师"
        DATETIME create_time "录入时间"
    }

    %% 关系定义
    USERS ||--o{ STUDENT : "管理/创建"
    USERS ||--o{ GRADE : "录入成绩"
    STUDENT ||--o{ GRADE : "拥有成绩"
    COURSE ||--o{ GRADE : "包含成绩"

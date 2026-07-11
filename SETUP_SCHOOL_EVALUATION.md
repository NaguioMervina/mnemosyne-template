# School Evaluation Feature - Quick Setup Guide

## ✅ Step-by-Step Implementation

### Step 1: Database Setup (5 minutes)

1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]
4. [[ITEM_4]]
5. [[ITEM_5]]
6. [[ITEM_6]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

[[CONTENT]]
```sql
SELECT * FROM school_evaluation_category;
SELECT * FROM school_evaluation_item;
-- You should see sample data populated
```

[[CONTENT]]

### Step 2: Add Routes (3 minutes)

[[CONTENT]]

[[CONTENT]]

```php
// ==========================================
// SCHOOL EVALUATION ROUTES
// ==========================================

// HRMS - Admin/Staff View
Route::group(['prefix' => 'hrms/school-evaluation', 'middleware' => ['auth', 'block.student']], function() {
    Route::get('/', 'SchoolEvaluationController@index');
    Route::get('/stats', 'SchoolEvaluationController@getEvaluationStats');
    Route::get('/overall', 'SchoolEvaluationController@getSchoolEvaluation');
    Route::get('/by-program', 'SchoolEvaluationController@getEvaluationByProgram');
    Route::get('/by-year-level', 'SchoolEvaluationController@getEvaluationByYearLevel');
    Route::get('/evaluators', 'SchoolEvaluationController@getEvaluators');
    Route::get('/student-detail', 'SchoolEvaluationController@getStudentEvaluationDetail');
    Route::get('/export', 'SchoolEvaluationController@exportEvaluation');
});

// Student Portal
Route::group(['prefix' => 'student/school-evaluation', 'middleware' => ['auth']], function() {
    Route::get('/', 'StudentSchoolEvaluationController@index');
    Route::get('/form', 'StudentSchoolEvaluationController@getEvaluationForm');
    Route::get('/check-status', 'StudentSchoolEvaluationController@checkSubmissionStatus');
    Route::post('/save', 'StudentSchoolEvaluationController@saveEvaluation');
    Route::post('/submit', 'StudentSchoolEvaluationController@submitEvaluation');
    Route::get('/view-submission', 'StudentSchoolEvaluationController@viewSubmission');
});
```

[[CONTENT]]
```bash
php artisan route:list | grep school-evaluation
# OR just visit: http://your-site.com/hrms/school-evaluation
```

[[CONTENT]]

### Step 3: Add Active Term/Semester Fields (2 minutes)

[[CONTENT]]

```sql
-- Add is_active column to term table
ALTER TABLE term ADD COLUMN is_active TINYINT(1) DEFAULT 0 AFTER term_name;

-- Add is_active column to semester_level table
ALTER TABLE semester_level ADD COLUMN is_active TINYINT(1) DEFAULT 0 AFTER semester_level_name;

-- Set your current active term (change the ID to your current term)
UPDATE term SET is_active = 0;
UPDATE term SET is_active = 1 WHERE id = 1; -- Change ID as needed

-- Set your current active semester
UPDATE semester_level SET is_active = 0;
UPDATE semester_level SET is_active = 1 WHERE id = 1; -- Change ID as needed
```

[[CONTENT]]

### Step 4: Add Navigation Links (5 minutes)

#### A. HRMS Menu

[[CONTENT]]

[[CONTENT]]

```html
<li>
    <a href="{{ url('hrms/school-evaluation') }}">
        <i class="fa fa-building"></i>
        <span>School Evaluation</span>
    </a>
</li>
```

#### B. Student Portal Menu

[[CONTENT]]

[[CONTENT]]

```html
<li>
    <a href="{{ url('student/school-evaluation') }}">
        <i class="fa fa-star"></i>
        <span>Evaluate School</span>
    </a>
</li>
```

[[CONTENT]]

### Step 5: Test the Feature (10 minutes)

#### Test as ADMIN/HRMS:

1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]
4. [[ITEM_4]]
5. [[ITEM_5]]

#### Test as STUDENT:

1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]
4. [[ITEM_4]]
5. [[ITEM_5]]
6. [[ITEM_6]]
7. [[ITEM_7]]
8. [[ITEM_8]]
9. [[ITEM_9]]

#### Verify HRMS View:

1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]
4. [[ITEM_4]]
5. [[ITEM_5]]

[[CONTENT]]

### Step 6: Customize Evaluation Items (Optional)

[[CONTENT]]

```sql
-- View current categories
SELECT * FROM school_evaluation_category;

-- View current items
SELECT * FROM school_evaluation_item;

-- Add a new category
INSERT INTO school_evaluation_category (category_name, description, order_by, is_active) 
VALUES ('Library Services', 'Evaluation of library facilities and services', 6, 1);

-- Add items for the new category (get the category_id first)
INSERT INTO school_evaluation_item (school_evaluation_category_id, item_name, order_by, is_active)
VALUES 
(6, 'Library has adequate book collections', 1, 1),
(6, 'Library staff are helpful and knowledgeable', 2, 1),
(6, 'Library hours are convenient', 3, 1);
```

[[CONTENT]]

## 🔧 Troubleshooting

### Issue: "Class not found" errors

[[CONTENT]]
```bash
composer dump-autoload
php artisan cache:clear
php artisan config:clear
php artisan view:clear
```

### Issue: Routes not working (404 error)

[[CONTENT]]
1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]

### Issue: "Table doesn't exist" error

[[CONTENT]]
```sql
SHOW TABLES LIKE '%school_evaluation%';
```
[[CONTENT]]

### Issue: Student can't see the form

[[CONTENT]]
1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]

### Issue: No statistics showing in HRMS

[[CONTENT]]
1. [[ITEM_1]]
2. [[ITEM_2]]
```sql
SELECT COUNT(*) FROM student_school_evaluation_form WHERE is_submit = 1;
```

[[CONTENT]]

## 📋 Quick Verification Checklist

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]
- [[ITEM_8]]
- [[ITEM_9]]
- [[ITEM_10]]
- [[ITEM_11]]
- [[ITEM_12]]

[[CONTENT]]

## 🎯 Next Steps After Setup

1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]
4. [[ITEM_4]]
5. [[ITEM_5]]
6. [[ITEM_6]]

[[CONTENT]]

## 📞 Need Help?

[[CONTENT]]
1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]
4. [[ITEM_4]]
5. [[ITEM_5]]

[[CONTENT]]

## 🚀 Quick Start Command Summary

```bash
# 1. Import database
mysql -u root -p your_database < database/migrations/create_school_evaluation_tables.sql

# 2. Clear caches
php artisan cache:clear
php artisan config:clear
composer dump-autoload

# 3. Test URLs
# HRMS: http://your-site.com/hrms/school-evaluation
# Student: http://your-site.com/student/school-evaluation
```

[[CONTENT]]

[[CONTENT]]

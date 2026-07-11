# School Evaluation Feature - Implementation Guide

## Overview
[[CONTENT]]

## Files Created

### 1. Controllers
- [[ITEM_1]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

- [[ITEM_2]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

### 2. Database Migration
- [[ITEM_1]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]
[[CONTENT]]

### 3. Views
- [[ITEM_1]]
- [[ITEM_2]]

### 4. Documentation
- [[ITEM_1]]

## Implementation Steps

### Step 1: Create Database Tables
[[CONTENT]]
```bash
mysql -u your_username -p your_database < database/migrations/create_school_evaluation_tables.sql
```

[[CONTENT]]

### Step 2: Create Model Files
[[CONTENT]]

```php
// app/Models/SchoolEvaluationCategory.php
<?php namespace App\Models;
use Illuminate\Database\Eloquent\Model;

class SchoolEvaluationCategory extends Model {
    protected $table = 'school_evaluation_category';
    protected $fillable = ['category_name', 'description', 'order_by', 'is_active'];
    
    public function items() {
        return $this->hasMany('App\Models\SchoolEvaluationItem', 'school_evaluation_category_id');
    }
}

// app/Models/SchoolEvaluationItem.php
<?php namespace App\Models;
use Illuminate\Database\Eloquent\Model;

class SchoolEvaluationItem extends Model {
    protected $table = 'school_evaluation_item';
    protected $fillable = ['school_evaluation_category_id', 'item_name', 'description', 'order_by', 'is_active'];
    
    public function category() {
        return $this->belongsTo('App\Models\SchoolEvaluationCategory', 'school_evaluation_category_id');
    }
}

// app/Models/SchoolEvaluationRemark.php
<?php namespace App\Models;
use Illuminate\Database\Eloquent\Model;

class SchoolEvaluationRemark extends Model {
    protected $table = 'school_evaluation_remark';
    protected $fillable = ['remark_value', 'description'];
}

// app/Models/StudentSchoolEvaluationForm.php
<?php namespace App\Models;
use Illuminate\Database\Eloquent\Model;

class StudentSchoolEvaluationForm extends Model {
    protected $table = 'student_school_evaluation_form';
    protected $fillable = [
        'student_id', 'term_id', 'semester_level_id', 
        'school_evaluation_category_id', 'school_evaluation_item_id',
        'school_evaluation_remark_id', 'grade', 'avg', 'is_submit'
    ];
}

// app/Models/SchoolEvaluationComment.php
<?php namespace App\Models;
use Illuminate\Database\Eloquent\Model;

class SchoolEvaluationComment extends Model {
    protected $table = 'school_evaluation_comment';
    protected $fillable = ['student_id', 'term_id', 'semester_level_id', 'comment'];
}
```

### Step 3: Add Routes
[[CONTENT]]

[[CONTENT]]
```php
// HRMS Routes
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

// Student Routes
Route::group(['prefix' => 'student/school-evaluation', 'middleware' => ['auth']], function() {
    Route::get('/', 'StudentSchoolEvaluationController@index');
    Route::get('/form', 'StudentSchoolEvaluationController@getEvaluationForm');
    Route::get('/check-status', 'StudentSchoolEvaluationController@checkSubmissionStatus');
    Route::post('/save', 'StudentSchoolEvaluationController@saveEvaluation');
    Route::post('/submit', 'StudentSchoolEvaluationController@submitEvaluation');
    Route::get('/view-submission', 'StudentSchoolEvaluationController@viewSubmission');
});
```

### Step 4: Add Navigation Links

[[CONTENT]]
[[CONTENT]]
```html
<li>
    <a href="{{ url('hrms/school-evaluation') }}">
        <i class="fa fa-building"></i> School Evaluation
    </a>
</li>
```

[[CONTENT]]
[[CONTENT]]
```html
<li>
    <a href="{{ url('student/school-evaluation') }}">
        <i class="fa fa-star"></i> Evaluate School
    </a>
</li>
```

### Step 5: Configure Term/Semester Activation
[[CONTENT]]

```sql
-- Add is_active field if not exists
ALTER TABLE term ADD COLUMN is_active TINYINT(1) DEFAULT 0;
ALTER TABLE semester_level ADD COLUMN is_active TINYINT(1) DEFAULT 0;

-- Set current active term/semester
UPDATE term SET is_active = 0;
UPDATE term SET is_active = 1 WHERE id = [current_term_id];

UPDATE semester_level SET is_active = 0;
UPDATE semester_level SET is_active = 1 WHERE id = [current_semester_id];
```

## Features

### For Students:
- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]

### For HRMS Admins:
- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]
- [[ITEM_8]]

## Customization Options

### 1. Modify Evaluation Categories
[[CONTENT]]
- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]

### 2. Modify Rating Scale
[[CONTENT]]

### 3. Add More Filters
[[CONTENT]]
- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]

### 4. Customize Email Notifications
[[CONTENT]]
- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]

## Testing Checklist

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
- [[ITEM_13]]
- [[ITEM_14]]

## Notes

1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]
4. [[ITEM_4]]
5. [[ITEM_5]]

## Support

[[CONTENT]]
1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]
4. [[ITEM_4]]
5. [[ITEM_5]]

## Future Enhancements

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]

# Validation Recipes

[[CONTENT]]

[[CONTENT]]

## Maintenance Notes

- [[ITEM_1]]
- [[ITEM_2]]
- [[ITEM_3]]

## Base Checks

[[CONTENT]]

```bash
git diff --check
git status --short
docker compose exec -T app php -l <file>
```

## Recipe: Apply Scholarship / Discount

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, term_name, is_active, is_current FROM term ORDER BY id DESC;"
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, semester_name, is_active, is_current, is_enrollment FROM semester_level ORDER BY id;"
```

2. [[ITEM_2]]

```bash
docker compose exec -T app php -l app/Http/Controllers/ApplyScholarshipController.php
```

3. [[ITEM_3]]

- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]

## Recipe: Cashiering Registration Fee

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, term_name, is_current, is_enrollment FROM term ORDER BY id DESC;"
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, semester_name, is_current, is_enrollment FROM semester_level ORDER BY id;"
```

2. [[ITEM_2]]

```bash
docker compose exec -T app php -l app/Http/Controllers/NewPaymentController.php
```

3. [[ITEM_3]]

- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]

## Recipe: Student Ledger Allow To Registration

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, classification_id, term_id, semester_level_id, is_active, is_current, is_enrollment FROM classification_term ORDER BY id DESC;"
```

2. [[ITEM_2]]

- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]

## Recipe: Payment Receipt Program Resolution

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T app php -l app/Http/Controllers/PaymentController.php
```

2. [[ITEM_2]]

- [[ITEM_3]]
- [[ITEM_4]]

## Recipe: TESDA AR Posting And Reports

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T app php -l app/Http/Controllers/ArUpdateController.php
docker compose exec -T app php -l app/Models/StudentLedger.php
docker compose exec -T app php -l app/Http/Controllers/Report/TesdaList.php
```

2. [[ITEM_2]]

```bash
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SHOW TABLES LIKE 'tesda_%'; SHOW COLUMNS FROM fee_type LIKE 'is_tesda'; SHOW COLUMNS FROM teacher LIKE 'is_tesda'; SHOW COLUMNS FROM student_ledger LIKE 'tesda_batch_id';"
```

3. [[ITEM_3]]

- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]
- [[ITEM_8]]
- [[ITEM_9]]

## Recipe: Student Clearance

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T app php -l app/Http/Controllers/StudentClearanceController.php
docker compose exec -T app php -l app/Http/Composers/StudentSidebarComposer.php
docker compose exec -T app php -l app/Models/CommonModel.php
```

2. [[ITEM_2]]

```bash
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SHOW CREATE TABLE student_clearance\\G SHOW CREATE TABLE student_clearance_module\\G"
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, menu, url, gen_role_id, shs_ordering_signature, college_ordering_signature, is_active FROM student_clearance_module ORDER BY id ASC;"
```

3. [[ITEM_3]]

- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]
- [[ITEM_8]]
- [[ITEM_9]]
- [[ITEM_10]]
- [[ITEM_11]]
- [[ITEM_12]]

## Recipe: Enrollment Term/Semester Handoff

[[CONTENT]]

1. [[ITEM_1]]
2. [[ITEM_2]]

- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]

## Recipe: Pre-Enroll Payment-Term Synchronization

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, description, amount, total_paid FROM student_payment_term WHERE student_id = <student_id> AND term_id = <term_id> AND semester_level_id = <semester_level_id> AND is_deleted = 0 ORDER BY id;"
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT payment_id, student_payment_term_id, amount_paid FROM student_payment_term_distribution WHERE student_id = <student_id> AND term_id = <term_id> AND semester_level_id = <semester_level_id> ORDER BY id;"
```

2. [[ITEM_2]]

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
- [[ITEM_15]]

## Recipe: Class List Examination PDF

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T app php -l app/Http/Controllers/GetClassList.php
```

2. [[ITEM_2]]

```bash
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, payment_term_description_name FROM payment_term_description WHERE id BETWEEN 3 AND 8 ORDER BY id;"
```

3. [[ITEM_3]]

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

## Recipe: UI Review For Dense Staff Screens

[[CONTENT]]

1. [[ITEM_1]]
2. [[ITEM_2]]
3. [[ITEM_3]]

- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]
- [[ITEM_8]]

## Recipe: Documentation-Only Mnemosyne Changes

[[CONTENT]]

1. [[ITEM_1]]

```bash
git diff --check
```

2. [[ITEM_2]]

- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]

## Recipe: Subject Fees Replication And Refresh

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T app php -l app/Http/Controllers/NewSchoolFeesController.php
```

2. [[ITEM_2]]

```bash
docker compose exec -T db mysql -uroot -prmmcdb -D rmmcdb_docker -e "SELECT id, classification_id, subject_id, program_id, fee_type_id, term_id, amount FROM subject_fees WHERE classification_id = <classification_id> AND term_id IN (<source_term_id>, <target_term_id>) ORDER BY subject_id, program_id, fee_type_id, term_id;"
```

3. [[ITEM_3]]

- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]
- [[ITEM_8]]

## Recipe: Public Or Staff Queue Safety

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T app php -l app/Http/Controllers/PublicQueuingSystemController.php
docker compose exec -T app php -l app/Http/Controllers/QueuingSystemController.php
```

2. [[ITEM_2]]

- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]

## Recipe: Admin Duplicate Student Review

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T app php -l app/Http/Controllers/AdminReportController.php
```

2. [[ITEM_2]]

- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]

## Recipe: Registrar Raw Data Export

[[CONTENT]]

1. [[ITEM_1]]

```bash
docker compose exec -T app php -l app/Http/Controllers/ImportController.php
docker compose exec -T app php artisan list | grep raw-data
```

2. [[ITEM_2]]

- [[ITEM_3]]
- [[ITEM_4]]
- [[ITEM_5]]
- [[ITEM_6]]
- [[ITEM_7]]

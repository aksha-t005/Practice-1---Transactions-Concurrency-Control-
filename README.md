# Practice-1---Transactions-Concurrency-Control-


-- 1. Create FeePayments table (if not exists)
CREATE TABLE IF NOT EXISTS FeePayments (
    payment_id INT PRIMARY KEY,
    student_name VARCHAR(100),
    amount DECIMAL(10,2),
    payment_date DATE
);

-- 2. Start the transaction
START TRANSACTION;

-- 3. Insert multiple fee payments
INSERT INTO FeePayments (payment_id, student_name, amount, payment_date) VALUES
(1, 'Ashish', 5000.00, '2024-06-01'),
(2, 'Smaran', 4500.00, '2024-06-02'),
(3, 'Vaibhav', 5500.00, '2024-06-03');

-- 4. Commit the transaction to make changes permanent
COMMIT;

-- 5. Verify the inserted records
SELECT * FROM FeePayments;

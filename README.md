# Brightlearn_exercise3_SQL_Case_statements
Demonstration of case statemnt queries.
SQL Foundations – Exercise 3: CASE Statements

Overview

This repository documents my third SQL practice exercise as part of the BrightLearn Data Analytics course.

The exercise focuses on using SQL CASE expressions to classify records into meaningful categories. It contains 10 queries across 10 tables and practises conditional logic, assigning labels, and predicting query output.

Learning Objectives

Through this exercise, I practise how to:

Write simple and searched CASE expressions inside a SELECT statement.

Combine CASE with comparison operators, BETWEEN, AND, and OR.

Classify records into business categories, such as price tiers, grades, and stock status.

Use AS to give a CASE result the required column name.

Predict the expected output table before running a query.

Tables and Datasets

Table

Description

products

Product names and prices, used to assign price categories.

orders

Customer orders and amounts, used to classify order values.

employees

Employee departments and salaries, used to assign position levels.

students

Student scores, used to assign letter grades.

deliveries

Delivery times, used to classify delivery performance.

tickets

Support issue types and priorities, used to label priority levels.

attendance

Days present and total days, used to calculate attendance percentages and statuses.

products_inventory

Product stock quantities, used to classify stock status.

classes

Subjects and enrolment counts, used to classify class sizes.

payments

Payment methods and amounts, used to determine discount eligibility.

Queries Covered

The 10 questions practise the following classifications:

Product price tiers — classify products as Expensive, Mid-range, or Budget.

Order value categories — classify orders as High Value, Medium Value, or Low Value.

Employee position levels — use department and salary conditions to assign Senior IT, Experienced HR, or Staff.

Student letter grades — convert numeric scores into grades from A to F.

Delivery performance — label deliveries as Fast, On Time, or Late.

Support ticket priority — convert numeric priorities into High, Medium, or Low.

Attendance status — calculate attendance percentage and classify it as Excellent, Good, or Needs Improvement.

Inventory stock status — classify stock as Out of Stock, Low Stock, or In Stock.

Class size categories — classify classes as Large, Medium, or Small based on enrolment.

Discount eligibility — check payment method and amount to determine whether a payment is Eligible for Discount or Not Eligible.

SQL Concepts Practised

CASE Expressions

A CASE expression evaluates conditions and returns a label or value for the first matching condition.

SELECT
    product_name,
    price,
    CASE
        WHEN price > 1000 THEN 'Expensive'
        WHEN price BETWEEN 100 AND 1000 THEN 'Mid-range'
        ELSE 'Budget'
    END AS price_category
FROM products;

Combining Conditions

CASE can combine conditions with operators such as AND and OR.

SELECT
    emp_name,
    department,
    salary,
    CASE
        WHEN department = 'IT' AND salary > 80000 THEN 'Senior IT'
        WHEN department = 'HR' AND salary > 55000 THEN 'Experienced HR'
        ELSE 'Staff'
    END AS position_level
FROM employees;

Calculated Values and Classification

A CASE expression can classify a calculated value, such as an attendance percentage.

SELECT
    student_id,
    (days_present * 100.0 / total_days) AS attendance_percentage,
    CASE
        WHEN (days_present * 100.0 / total_days) >= 90 THEN 'Excellent'
        WHEN (days_present * 100.0 / total_days) >= 75 THEN 'Good'
        ELSE 'Needs Improvement'
    END AS attendance_status
FROM attendance;

These examples illustrate concepts practised in the exercise; the complete assignment requires writing all 10 queries and drawing their expected output tables.

Key Learning

This exercise develops my understanding of how SQL can transform raw values into meaningful categories. Instead of returning only a number, a query can use conditional logic to produce labels that are easier to interpret in business contexts.

I am practising how to order WHEN conditions, combine multiple conditions, calculate values, and use AS to match the required output column names.

Exercise Format

The original assignment is a handwritten, pen-and-paper activity. Each question requires writing the full SQL query and drawing the expected output table by hand. The output must use the exact column names specified in the assignment.

Course Information

Course: BrightLearn Data Analytics

Module: SQL Foundations

Exercise: 03

Topic: SQL CASE Statements

Exercise format: Handwritten SQL queries and expected output tables

Repository Purpose

This repository forms part of my Data Analytics learning journey. It documents my progress in SQL, from retrieving and filtering data to using conditional logic to classify records.

Status: SQL Foundations – Exercise 3

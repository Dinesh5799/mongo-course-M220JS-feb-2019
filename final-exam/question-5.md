# Question 5
## Problem
Given the following bulk write statement, to a collection called employees:

const baseballPlayers = [
  insertOne({ _id: 11, name: 'Edgar Martinez', salary: "8.5M" }),    // Insert #1
  insertOne({ _id: 3, name: 'Alex Rodriguez', salary: "18.3M" }),    // Insert #2
  insertOne({ _id: 24, name: 'Ken Griffey Jr.', salary: "12.4M" }),  // Insert #3
  insertOne({ _id: 11, name: 'David Bell', salary: "2.5M" }),        // Insert #4
  insertOne({ _id: 19, name: 'Jay Buhner', salary: "5.1M" })         // Insert #5
]

const bulkWriteResponse = employees.bulkWrite(baseballPlayers)

Assume the employees collection is empty, and that there were no network errors in the execution of the bulk write.

Which of the insert operations in requests will succeed?

Check all answers that apply:

Insert #1
Insert #2
Insert #3
Insert #4
Insert #5

### My answer
Insert #1
Insert #2
Insert #3

Why? Adding `{ordered: false}` as an option to bulkWrite would allow commands to execute in parralel. Otherwise, they will be executed until the first error is hit - which is a duplicate key error when attempting to insert the fourth item.
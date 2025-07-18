# 🚀 Project 1: Exploring AWS Identity and Access Management (IAM)

## 🌟 Project Goal

The goal of this project is to understand the basics of IAM (Identity and Access Management) in AWS, including how to create users, user groups, attach permissions, and test access based on different policies.



---

## 🛠️ AWS Console Steps

### 🔍 Step 0: Search for IAM

- Go to the AWS Console.
- In the search bar, type `IAM`.

---

### 👥 Step 1: Create IAM Users

- Create the following users:
  - `user-1`
  - `user-2`
  - `user-3`
- ✅ Grant them access to **AWS Management Console**.
- ✅ Set a custom password and **write it down (Clipboard)** to use later.

---

### 🢑 Step 2: Create User Groups

- Navigate to **User Groups**.
- Create 3 groups:
  - `EC2-admin`
  - `EC2-support`
  - `S3-support`

---

### 🔐 Step 3: Configure EC2-support Group

- Attach the policy: `AmazonEC2ReadOnlyAccess`

> ℹ️ This policy allows the user to **view EC2, S3, CloudWatch, EC2 Auto Scaling**, but they **cannot create, modify, or delete** any resource.

---

### 📜 Step 4: Understand the JSON Policy Structure

Go to the attached policy → click on **JSON** tab.

You will see:

```json
{
  "Effect": "Allow",
  "Action": "ec2:Describe*",
  "Resource": "*"
}
```

- **Effect**: Specifies whether the statement allows or denies access (`Allow` or `Deny`).
- **Action**: Lists the API actions allowed (e.g., `ec2:DescribeInstances`).
- **Resource**: Specifies which resources the actions apply to.

---

### 📦 Step 5: Configure S3-support Group

- Attach policy: `AmazonS3ReadOnlyAccess`

> ℹ️ This policy gives the user permission to **view and list S3 buckets**, but **cannot modify, delete, or create** any bucket.

---

### 🛠️ Step 6: Configure EC2-admin Group

- Attach a custom policy called `EC2-Admin-Policy`.

❓ **Question**: What does this policy mean?

```json
{
  "Effect": "Allow",
  "Action": "ec2:*",
  "Resource": "*"
}
```

> ✅ This means the user has **full administrative access to EC2** (can create, modify, delete, start, stop instances, etc.).

---

### 👤 Step 7: Add Users to Groups

| User   | Group       |
| ------ | ----------- |
| user-1 | S3-support  |
| user-2 | EC2-support |
| user-3 | EC2-admin   |

**Steps**:

1. Go to **User Groups**.
2. Select a group (e.g., `S3-support`).
3. Click **Add users**.
4. Select the user (e.g., `user-1`) → click **Add user**.
5. Repeat for the other groups.

---

## 🔐 Step 8: Sign in as IAM Users

### As `user-1`:

1. Go to **IAM** → **Users** → `user-1` → **Security Credentials**.
2. Copy the **Console sign-in link**.
3. Open it in an incognito tab.
4. Enter:
   - Username: `user-1`
   - Password: (the one saved earlier)
5. Search for **S3** → confirm that you can view existing buckets but **not create or delete** any.

### As `user-3`:

1. Same steps, but login as `user-3`.
2. Search for **EC2** → go to **Instances**.
3. Try to launch or stop instances (if available).

---

## 🧐 Notes & Reflections

- IAM is the **foundation of secure AWS access**.
- Applying the **Least Privilege Principle** ensures that users only get the access they really need.
- JSON policies are **highly customizable**, and understanding their structure is essential for real-world AWS work.

---

## ✅ Project Completed

Thanks for reading!\
Looking forward to seeing you in the next project!


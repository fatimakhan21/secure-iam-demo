🔐 AWS IAM Least Privilege Demo

This is a beginner-friendly hands-on project where I created a restricted IAM user and tested how AWS enforces least-privilege access using the AWS CLI.

STEP 0: Before you start

✔ Log into your AWS account
✔ Open IAM in the AWS Console
✔ Create a folder on your laptop called:
AWS-IAM-Screenshots

📸 Every time I say TAKE A SCREENSHOT, save it there.

STEP 1: Create a restricted IAM user

Open IAM → Users → Add user

Username: limited-s3-user

Access type: Programmatic access only

Do not attach any permissions yet

Finish creating the user

📸 TAKE SCREENSHOT #1
👉 Screenshot the user details page (shows limited-s3-user)

STEP 2: Attach limited permissions

Open limited-s3-user

Go to the Permissions tab

Click Add permissions

Attach a restricted policy (or no permissions)

Save changes

📸 TAKE SCREENSHOT #2
👉 Screenshot the Permissions section showing limited or no access

✍️ Note for later writing:

“I learned that IAM users don’t have access to anything by default. Permissions must be explicitly granted.”

STEP 3: Configure AWS CLI

Open your terminal

Run:

aws configure


Enter:

Access Key ID

Secret Access Key

Default region: eu-north-1

Output format: json

📸 TAKE SCREENSHOT #3
👉 Screenshot showing AWS CLI configured

STEP 4: Test restricted access

Run:

aws s3 ls


Expected result: AccessDenied

📸 TAKE SCREENSHOT #4
👉 Screenshot the AccessDenied message

✍️ Note:

“This confirmed that my IAM user could not list all S3 buckets and that least-privilege was working.”

STEP 5: STOP ✋ (do not change permissions yet)

At this point I had:

✔ A restricted IAM user
✔ AWS CLI configured
✔ Proof of AccessDenied
✔ 4 screenshots
✔ Personal learning notes

🎉 This shows that least-privilege is enforced.

What I Learned

IAM users start with no permissions by default

Permissions must be explicitly granted using policies

Least-privilege reduces security risks

Testing with AWS CLI helps verify access behavior

AccessDenied errors are useful confirmation, not failures

Screenshots

IAM user created (limited-s3-user)

Permissions overview (restricted access)

AWS CLI configuration

AccessDenied when listing S3 buckets

⚠️ All screenshots are from my personal AWS account.
No secret keys, account numbers, or sensitive information are included.

Final Thoughts

This project helped me understand how IAM enforces least-privilege and why restricted users are important for cloud security.
Seeing AccessDenied in real life made the concept much clearer than just reading about it.

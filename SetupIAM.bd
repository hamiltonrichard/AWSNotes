# IAM Administrator Account Setup

To create an administrative user with full operational access to deploy resources but absolutely no access to billing and cost management data, you need to use AWS Identity and Access Management (IAM).

AWS handles this beautifully by keeping administrative permissions separate from billing permissions. By default, even a user with the managed `AdministratorAccess` policy **cannot** view billing details unless explicit root-level access is granted—but to be absolutely safe, you can explicitly deny billing access.

Here is the step-by-step guide to setting this up using the AWS Console.

---

## Step 1: Create a Custom "Deny Billing" Policy

While the standard administrator policy doesn't automatically grant billing access to IAM users anymore, creating an explicit **Deny** policy acts as an iron-clad guardrail.

1. Sign in to the AWS Management Console (ideally as your Root user or your primary admin).
2. Navigate to the **IAM Console** (Identity and Access Management).
3. In the left navigation pane, click **Policies**, then click **Create policy**.
4. Click the **JSON** tab and replace the existing text with the following policy:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ExplicitDenyBillingAndCost",
            "Effect": "Deny",
            "Action": [
                "aws-portal:*Billing*",
                "aws-portal:*Usage*",
                "billing:*",
                "ce:*",
                "cur:*",
                "pricing:*",
                "budgets:*"
            ],
            "Resource": "*"
        }
    ]
}

```

5. Click **Next: Tags** (optional), then **Next: Review**.
6. Name the policy something clear, like `DenyBillingAndCostManagement`.
7. Click **Create policy**.

---

## Step 2: Create the IAM User and Attach Policies

Now, you will create the actual user account and attach both the standard AWS Administrator access and your new safety restriction.

1. In the left navigation pane of the IAM Console, click **Users**, then click **Create user**.
2. **User details:** Enter a user name (e.g., `ops-admin`).
3. Check the box for **Provide user access to the AWS Management Console**.
4. Choose **I want to create an IAM user** (if you want standard password management) and set your password preferences. Click **Next**.
5. **Set permissions:** Select **Attach policies directly**.
6. In the permissions policies search box, find and check the following **two** policies:
* **`AdministratorAccess`** (This is an AWS-managed policy that grants full operational power to deploy any resource).
* **`DenyBillingAndCostManagement`** (The custom policy you created in Step 1).


7. Click **Next** to review, and then click **Create user**.

> ⚠️ **Why this works:** In AWS IAM, an explicit `Deny` always overrides an `Allow`. Even though `AdministratorAccess` technically says "allow everything," your custom policy says "deny billing," so billing will be blocked completely.

---

## Step 3: Verify the Root Account Billing Setting (Crucial Check)

AWS has a global account setting that controls whether *any* IAM users can see billing, regardless of their individual policies. Let's make sure it's tight.

1. Sign in to the AWS Console using your **Root user account** (the email address used to create the AWS account).
2. Click your account name in the top-right corner and select **Account**.
3. Scroll down to the **IAM User and Role Access to Billing Information** section.
4. Click **Edit**.
5. Ensure that **Activate IAM Access** is checked if you want *other* specific roles to ever see it, but rest assured that your new `ops-admin` user is fully blocked by the explicit `Deny` policy you attached to them. If you want a blanket ban for all IAM entities across the entire account, you can uncheck this box entirely.

---

### Step 4: Test the Account

Log in to the AWS console using your new `ops-admin` credentials. Try to spin up an EC2 instance or an S3 bucket to verify your deployment powers work perfectly. Then, attempt to navigate to the **Billing and Cost Management** console—you should be greeted with an "Access Denied" or "You need permissions" message.


Logging in as the AWS Root user requires using the **email address** you used to first create the AWS account, rather than an IAM username.

Here is exactly how to do it:

---

## The Root Login Process

1. Go to the [AWS Management Console Sign-In Page](https://signin.aws.amazon.com/).
2. Select the **Root user** radio button.
3. Enter the **Email address** associated with the AWS account and click **Next**.
4. Complete the security captcha check if prompted.
5. Enter your account **Password** and click **Sign in**.
6. If you have Multi-Factor Authentication (MFA) enabled (which is highly recommended for root), enter your authentication code from your authenticator app or hardware device.

---

## ⚠️ Essential Security Best Practices for the Root User

Because the Root user has absolute control over every aspect of your account—including billing, deleting the account, and changing structural settings—you should minimize its use.

* **Enable MFA Immediately:** If you haven't already, set up Multi-Factor Authentication on the root account right away. This is your single most critical line of defense.
* **Lock it Away:** Once you have created your daily operational admin account (like the one we set up previously), log out of the root account.
* **Use Only for Specific Tasks:** Only log back into root when absolutely necessary. AWS requires root access for only a few specific tasks, such as:
* Changing your AWS support plan.
* Changing your account name, root password, or root email address.
* Closing the AWS account entirely.
* Enabling IAM user access to the billing console (as mentioned in the previous setup).



Are you running into an error (like an invalid password or locked MFA) trying to get into the root account?
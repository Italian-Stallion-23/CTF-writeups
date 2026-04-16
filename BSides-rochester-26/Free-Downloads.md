# BSides Rochester 2026 - MetaCTF Challenge: Free Downloads

## Challenge Description
Your friends are bragging about a flag downloading service, but no one is willing to share where you can get a license to access it. The goal was to figure out how to bypass the restrictions and retrieve the flag without a valid license.

## Objective
The goal of this challenge was to bypass client-side input validation and gain access to the restricted flag download page.

## Tools Used
- Web browser developer tools (Inspect Element)
- Regex analysis
- Manual input testing

## Steps

### 1. Initial Observation
I accessed the provided website and noticed a form requiring a license key to proceed.

### 2. Analyzing Client-Side Validation
Using browser developer tools, I inspected the page source and identified a JavaScript/regex validation rule controlling acceptable input.

The validation pattern required input matching:
# BSides Rochester 2026 - MetaCTF Challenge: Free Downloads


""function check_key() {
  ""var key = $("#license_key").val();
  ""if (key.match(/^[a-z]{2}[12345][6789]-[0-9A Za-z]{4}-Z\d{2}W-[A-z0]{4}$/i)) {
    window.location.href = "./authenticated_flag_download_page.php";
  } else {
    $("#error_message").slideDown();
  }
}""


'^[a-z]{2}[12345][6789]-[0-9A-z]{4}-Z\d{2}W-[A-z0]{4}$'

This breaks down as:
- 2 lowercase letters
- 1 digit (1–5)
- 1 digit (6–9)
- dash
- 4 alphanumeric characters
- dash
- Z + 2 digits + W
- dash
- 4 characters (letters or 0)

### 3. Bypassing Validation
Since validation was client-side, I bypassed it by manually entering a valid format directly into the input field:

ab16-ABCD-Z12W-0000

### 4. Retrieving the Flag
After submitting the bypassed input, access was granted and the flag was displayed.

## Flag
MetaCTF{REPLACE_WITH_FLAG}

## Key Takeaways
- Learned how client-side validation can be bypassed
- Practiced analyzing regex patterns in web applications
- Understood that frontend validation should not be trusted for security

<img width="1387" height="643" alt="bsidesweb1" src="https://github.com/user-attachments/assets/18dfe859-0ddd-4166-a18a-0a1de2304cc9" />




<img width="1547" height="425" alt="bsidesweb2" src="https://github.com/user-attachments/assets/d2b127ea-ce76-407d-b028-98e9c7e86d32" />




# Blue Team CTF – Solution / Writeup

**Question 1:** Who is the primary recipient of this email?  
**Answer:** jane.smith@company.com  
*Explanation:* Found in the `To:` field of the email.

**Question 2:** What is the subject of the email?  
**Answer:** Urgent: Overdue Invoice - Action Required  
*Explanation:* Taken from the `Subject:` field.

**Question 3:** What is the date and time the email was sent?  
**Answer:** 29-Mar-2026 10:15:00 +0200  
*Explanation:* Found in the `Date:` field of the email.

**Question 4:** What is the sender domain?  
**Answer:** secure-payments.com  
*Explanation:* Extracted from the sender email `billing@secure-payments.com`.

**Question 5:** Perform a WHOIS lookup on the sender domain. What is the registrar name?  
**Answer:** GoDaddy.com, LLC (example)  
*Explanation:* WHOIS shows the domain registrar.

**Question 6:** Is the display text of the hyperlink in the email the same as the actual URL? If not, what is the real URL?  
**Answer:** No, the display text says “View Your Invoice,” but the actual URL is `http://secure-payments-verify.com/invoice?id=45987`  
*Explanation:* Inspecting the HTML shows a mismatch, which is a common phishing technique.

**Question 7:** What is the name of the attached file?  
**Answer:** attachment.docx  
*Explanation:* The filename from the email attachment.

**Question 8:** Using URL2PNG (or screenshot method), what is the heading text on the webpage the link points to?  
**Answer:** Secure Payments Verification  
*Explanation:* Simulated screenshot shows the webpage heading.

**Question 9:** Based on the email content and attachment, what suspicious indicators suggest this email is phishing? (list at least 2)  
**Answer:**  
1. Link text does not match the actual URL  
2. Urgency and threat in email content  
3. Unexpected attachment  
*Explanation:* These are common phishing indicators analyzed by a SOC analyst.

**Question 10:** What is the flag hidden in the attachment?  
**Answer:** DGF{attachment_reviewed}  
*Explanation:* Found inside `attachment.docx`.

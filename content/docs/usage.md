---
title: 'Usage'
date: 2019-04-08
weight: 20
description: This page includes information on how you can use Formgate as well as some example forms you can use.
---

- [Request Parameters](#params)
- [Example Forms](#examples)
    - [Basic Example](#basic-example)
    - [File Example](#file-example)

# <a name="params"></a> Request Parameters

Send a POST request to `https://forms.yourdomain.com/send` with the following parameters:

| Name              | Value                                                                             |
| ------------------| ----------------------------------------------------------------------------------|
| _recipient        | The recipient email address for this contact form.                                |
| _redirect_success | The URL to redirect to after a successful form submission. (optional)             |
| _sender_name      | The sender name for this contact form. (optional)                                 |
| _sender_email     | The sender email address for this contact form. (optional)                        |
| _subject          | The subject line for this contact form. (optional)                                |
| _hp_email         | If this field is filled in then a 422 error will be returned. (optional)          |
| file              | An input file which will be attached to the email (optional)                      |

**Notes:**

The `_recipient` **must** be added to the allow list in your `.env` file to be valid.

The `_hp_email` field acts as a honeypot field to prevent spam submissions.

Any other parameters you include will be shown in the generated email automatically.

# <a name="examples"></a> Example Forms
You can see some example forms below ranging from super basic to much more advanced (coming soon).

## <a name="basic-example"></a> Basic Example

```html
<form action="https://forms.yourdomain.com/send" method="POST">
  <input type="hidden" name="_recipient" value="someone@clientwebsite.com">
  <input type="hidden" name="_redirect_success" value="https://clientwebsite.com/success/">
  <input type="text" name="_sender_name" placeholder="Your Name">
  <input type="email" name="_sender_email" placeholder="Your Email">
  <input type="text" name="_subject" placeholder="Your Subject">
  <textarea name="Message" placeholder="Your Message"></textarea>
  <input type="submit" value="Send">
</form>
```

## <a name="file-example"></a> File Example

```html
<form action="https://forms.yourdomain.com/send" method="POST" enctype="multipart/form-data">
  <input type="hidden" name="_recipient" value="someone@clientwebsite.com">
  <input type="hidden" name="_redirect_success" value="https://clientwebsite.com/success/">
  <input type="text" name="_sender_name" placeholder="Your Name">
  <input type="email" name="_sender_email" placeholder="Your Email">
  <input type="text" name="_subject" placeholder="Your Subject">
  <textarea name="Message" placeholder="Your Message"></textarea>
  <input type="file" name="file">
  <input type="submit" value="Send">
</form>
```
**Formgate will attach any file that is uploaded to the server. You should use the HTML [accept attribute](https://www.w3schools.com/tags/att_input_accept.asp) to limit what can be uploaded.**

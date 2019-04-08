---
title: 'Usage'
date: 2019-04-08
weight: 20
description: Lorem ipsum dolor sit amet, consectetur adipisicing elit. Doloremque corporis voluptates, omnis porro quas adipisci, deleniti maxime eaque possimus nostrum nulla et illo earum ex minus aliquid reiciendis odit rem.
---

- [Request Parameters](#params)
- [Example Forms](#examples)
    - [Basic Example](#basic-example)

# <a name="params"></a> Request Parameters

Send a POST request to `https://forms.yourdomain.com/send` with the following parameters:

| Name              | Value                                                                 |
| ------------------| ----------------------------------------------------------------------|
| _recipient        | The recipient email address for this contact form.                    |
| _redirect_success | The URL to redirect to after a successful form submission. (optional) |
| _sender_name      | The sender name for this contact form. (optional)                     |
| _sender_email     | The sender email address for this contact form. (optional)            |
| _subject          | The subject line for this contact form. (optional)                    |

**Important:** The `_recipient` must be added to the allow list in your `.env` file to be valid.

You can include any other parameters to be included in the generated email.

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

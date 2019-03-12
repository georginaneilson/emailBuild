# Emails
Download the sass version of Zurb's Fountation email framework
`npm install --global foundation-cli`
`foundation new --framework emails`

Errored for me on install with "Node Sass does not yet support your current environment: Windows 64-bit with Unsupported runtime (57)" so had to cd into project folder, change "gulp-sass": "x.x.x" in package.json to   "gulp-sass": "^3.1.0" and npm install again

Run `foundation watch` to start the local server. Gives you a bunch of email templates to work with and scss files. It's written using Inky syntax but I find it easier/more customisable to go into the Dist folder and grab the full HTML files (table madness) to work on. But work in the src folder as the dist folder is overwritten on cmd+s. 

Run `npm run build` when the email is complete to inline the styles etc ready to be grabbed from the Dist folder.

Foundation comes with its own buttons but I'd recommend using the padding and border based button [from Litmus](https://litmus.com/blog/a-guide-to-bulletproof-buttons-in-email-design).

Don't forget your preheaders. This is the  first 90 characters in your email and displayed just below the subject line. 90 characters too long? Just add hunners of `&nbsp;&zwnj;`s  (actually, [read this article first!](https://litmus.com/blog/the-little-known-preview-text-hack-you-may-want-to-use-in-every-email) )

**Test test test** every change on Litmus. Email clients and operating systems render everything different. Make sure you get the Engineer to send the final draft to your litmus email so you can test how it looks being send through the script. 

## Checklist

- Run gulp build to inline styles
- Preheader filled out
- Tested final email on Litmus against the major supported email clients and OS systems (both pasted code and sent via email code)
- Tested physically on your phones for responsiveness
- All style tag {}s duplicated for the python script ie. ` table.body center {{min-width: 0 !important}}`
- Beautified HTML in dist folder before passing to the engineer
- Had the engineer send a final draft to the Litmus account from the python script


#### Useful links

- Foundation framework | https://foundation.zurb.com/emails/getting-started.html
- Foundation docs | https://foundation.zurb.com/emails/docs/index.html
- Adding an empty column | https://foundation.zurb.com/forum/posts/35362-empty-columns
- Bulletproof email buttons | https://litmus.com/blog/a-guide-to-bulletproof-buttons-in-email-design
- Email inspiration (and code) | https://reallygoodemails.com/
- Gmail quirks | https://www.emailonacid.com/blog/article/email-development/12_things_you_must_know_when_developing_for_gmail_and_gmail_mobile_apps-2/
- Preheader hack | https://litmus.com/blog/the-little-known-preview-text-hack-you-may-want-to-use-in-every-email

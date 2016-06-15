#Email Code Standards   

## Table of Contents
1. Resources
2. General Rules
3. Head Elements `<head>`
    1. Doctype
    2. CSS `<style>`
4. Body Elements `<body>`
	1. Tables `<table>`
	2. Table Divs `<td>`
	3. Table Rows `<tr>`   
	4. Images `<img>`
5. Formatting 
6. Mobile/Responsive
	1. Mobile Header Styles
	2. Tips for Mobile/Responsive Emails


* * *  	

##1. Resources: 

This list is important due to the fact that email clients are growing their rendering capabilities constantly. 
It's important to stay up to date with what is new, and update this document accordingly. 

####Responsive Email Patterns
This is a wonderful resource that gives you examples of many different layouts and shows how each pattern is supported across email clients.

[A collection of patterns & modules for responsive emails](http://responsiveemailpatterns.com/)

####Most Up To Date Responsive Layout Email Articles
[DEVELOPMENT RESOURCES - THE ULTIMATE GUIDE](https://www.campaignmonitor.com/dev-resources/)
[Responsive emails that really work](https://codeascraft.com/2014/03/13/responsive-emails-that-really-work/)  
[Creating a Simple Responsive HTML Email](http://webdesign.tutsplus.com/articles/creating-a-simple-responsive-html-email--webdesign-12978)

####Campaign Monitor - GUIDES
[DEVELOPMENT RESOURCES - THE ULTIMATE GUIDE](https://www.campaignmonitor.com/dev-resources/)
[MOBILE EMAILS](http://www.campaignmonitor.com/guides/mobile/)  
[MOBILE EMAIL DESIGN](http://www.campaignmonitor.com/guides/mobile/design/)  
[CODING MOBILE EMAILS](https://www.campaignmonitor.com/guides/mobile/coding/)  
[CODING RESPONSIVE EMAILS](https://www.campaignmonitor.com/guides/mobile/responsive/)  
[TARGETING DEVICES WITH MEDIA QUERIES](https://www.campaignmonitor.com/guides/mobile/targeting/)  
[OPTIMIZING IMAGES FOR MOBILE](https://www.campaignmonitor.com/guides/mobile/optimizing-images/)  
[WILL IT WORK?](https://www.campaignmonitor.com/resources/will-it-work/)
[CSS SUPPORT](http://www.campaignmonitor.com/css/)  
[RESOURCES](https://www.campaignmonitor.com/resources/)

####MailChimp - GUIDES
[MAILCHIMP TEMPLATE TIPS - EMAIL DESIGN](http://templates.mailchimp.com/design/)
[MAILCHIMP TEMPLATE TIPS - EMAIL DEVELOPMENT](http://templates.mailchimp.com/development/)

####Litmus - Templates Useful for pulling HTML for layout
[LITMUS TEMPLATES - HTML DOWNLOADS](https://litmus.com/community/templates)

####Email On Acid
[DEVELOPMENT RESOURCES](https://www.emailonacid.com/blog/email-development)

* * *  
 
##2. General Rules:

With so many email clients out there, it's hard to be consistent with each. These rules are in place to make emails render the same from one email client to another. The following will also help make code more readable (which is especially important when troubleshooting rendering errors).

-  NEVER use PNGs - Use JPGs instead. 

-  Use JPG image optimizer

-  Always have 2x icon images and other images that need to be 2x for Retina display.

-  Use as little commenting as possible in emails or you risk spam banishment.

-  Always use inline styles as well as header styles.

-  Always use HTML entities. Instead of `&` use `&amp;`  
   [List of all HTML entities](http://www.w3schools.com/html/html_entities.asp)

-  Put `<br>` tags or groups of `<br>` tags on their own line

-  Don't use margins. If you use padding, use on `<td>` and not on `<p>` tags. Gmail doesn't read padding on `<p>` tags.

-  Don't give height to <table>, <td>, or <tr>

* * *  

##3. Head Elements `<head>`   
 
###3.1 Doctype

This is a great DOCTYPE to test with because it is used by Gmail and Hotmail. It is very important to test with and without     
a DOCTYPE because many clients strip it entirely - this effects paragraph margins & padding, centering, and box model padding.    
      
For more information on how the DOCTYPE effects your email, check out the following resources:
[http://www.emailonacid.com/blog/details/C18/doctype_-_the_black_sheep_of_html_email_design](http://www.emailonacid.com/blog/details/C18/doctype_-_the_black_sheep_of_html_email_design)   
[http://www.campaignmonitor.com/blog/post/3317/correct-doctype-to-use-in-html-email/](http://www.campaignmonitor.com/blog/post/3317/correct-doctype-to-use-in-html-email/)    

	<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

	<html xmlns="http://www.w3.org/1999/xhtml">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
		<title>Your Message Subject or Title</title>
		<style type="text/css">
		
###3.2 CSS

Originally based on The MailChimp Reset from Fabio Carneiro,   
MailChimp User Experience Design
More info and templates on Github: [https://github.com/mailchimp/Email-Blueprints](https://github.com/mailchimp/Email-Blueprints)   

	
		#outlook a {padding:0;} 

		body{width:100% !important; -webkit-text-size-adjust:100%; -ms-text-size-adjust:100%; margin:0; padding:0;}

		.ExternalClass, .ExternalClass p, .ExternalClass span, .ExternalClass font, .ExternalClass td, .ExternalClass div {line-height: 100%;}
		#backgroundTable {margin:0; padding:0; width:100% !important; line-height: 100% !important;}

		img {outline:none; text-decoration:none; -ms-interpolation-mode: bicubic;}  
		a img {border:none;}  
		.image_fix {display:block;}  

		a:hover {text-decoration: none !important;}

		html, body{ background-color: #f1f1f1; color: #352b21; }
		a, img, .links, .links a{ border: 0; outline: 0; color: #352b21; text-decoration: underline; padding: 0; margin: 0; }
		a:hover { color: #e84c3d: }
		table {mso-table-lspace:0pt; mso-table-rspace:0pt;border:0}
		table td {border-collapse: collapse;}
		table tr {border-collapse: collapse;}
		p {margin: 0; padding: 0;}


* * *  

##4. Body Elements `<body>`

###4.1 Tables:   

- For a strict width layout, define the width of the `<table>` element    
  For a more fluid layout, do NOT define width of the specific or use 100% width `<table>` 
	
- Wrapper/Container Table:   
  Use a wrapper table to control the width and the background color consistently of your email. Use this approach instead of setting attributes on the body tag.

  `<table cellpadding="0" cellspacing="0" border="0" id="backgroundTable">`	
	
-  Tables are the most common way to format your email consistently.    
   Set your table widths inside cells and in most (always) cases reset cellpadding, cellspacing, and border to zero.    
   Use nested tables as a way to space effectively in your message.

-  A bug on the iPad and iPhone renders what looks like small borders around `<td>` tags (especially noticable with a dark background). Make sure to give your `<table>` tags a `bgcolor=""` to fix this. This issue occurs when a template is not made mobile responsive and the original email template is scaled down on these devices. 

- If at all possible do NOT use height on `<table>` elements at all. In the case of a self serve template, this will cause a white space below an image because the height of an image is set to auto in responsive email design.
	
###4.2 Table Rows:  
- No styles belong on `<tr>` elements. 

- Always open and close `<tr>` elements on their own line for better legibility. 

###4.3 Table Divs:

- Set all styles inline on `<td>` elements.
	
###4.4 Images:

-   Always save out small images that do not change scale in mobile devices (social icons, logos, social sharing icons, buttons) out as a 2x version. This is so that Retina screens render them clearly. 

-	Always use absolute paths for images from thepinkboa. Example:   
 	(http://thepinkboa.com/clients/gatlinburg/2012/12-GBG-0100-april-co-op/coded/img/bg-top-left.jpg )

-   Always Give `img` elements `display: block; border: none;` 

- If at all possible do NOT use height on `img` elements at all. In the case of a self serve template, this will cause a white space below an image because the height of an image is set to auto in responsive email design.

* * *  

##5. Formatting: Only indent when nesting `<table>` inside of `<td>`
###For example:
		
	<table>
	<tr>
	<td>
		<table>
		<tr>
		<td>
		Your content goes here. 
		</td>
		</tr>
		</table>
	</td>
	</tr>
	</table>


* * *  	
   
##6. Mobile/Responsive

###6.1 Mobile Targeting Head Styles

Use @media queries with care.  
You should not bring these styles inline -- 
so it's recommended to apply them AFTER you bring the other stlying inline. 

####This is an example of header styles for mobile devices

			@media only screen and (max-device-width: 480px) {
			    div[class="header"] {
			        font-size: 16px !important;
			    }
			    table[class="table"], td[class="cell"] {
			        width: 325px !important;
			    }
				table[class="promotable"], td[class="promocell"], td[class="contentblock"] {
			        width: 325px !important;
					padding: 0px 20px 0px 20px;
			    }
				td[class="events"] {
					padding: 20px 5px 0 5px !important;
					border-bottom: 1px solid #666666 !important;
				}
				td[class="starter"] {
					padding: 20px 0 0 0 !important;
				}
				td[class="footershow"] {
			        width: 325px !important;
			    }
				table[class="hide"], img[class="hide"], td[class="hide"] {
			        display: none !important;
			    }
			    img[class="divider"] {
				    width: 325px !important;
				}
				table[class="show"], td[class="show"] {
					display: block !important;
					background-color: #ffffff;
					padding: 10px 0px;
				}
				td[class="show"] {
					width: 20px;
				}
				a[class="nav"] {
					font-family:'Helvetica', sans-serif;
					font-size: 14px;
					font-weight: bold;
					text-decoration: none;
					color: #574939;
					width: 100%;
				}
			}

		<!--[if gte mso 9]>
		<style>
			/* Target Outlook 2007 and 2010 */
		</style>
		<![endif]-->

	</head>

###6.2 Tips for Mobile/Responsive Emails

-   THE MINIMUM FONT SIZE DISPLAYED ON AN IPHONE IS 13PX. Keep this in mind when styling text, because anything smaller will be upscaled and could break your layout. Alternately, you can override this behavior in your style sheet (do so with care).  
  
-   When possible, use `display: none;` to hide extraneous details in your mobile layout. Elements like social sharing buttons may be great in the desktop inbox, but aren't always easy to use by the recipient on mobile devices. 
	
-   Consider using progressive disclosure in mobile for clients with lots of copy.   

      
####To avoid email rendering as mobile version in Yahoo! Mail, use ATTRIBUTE SELECTOR format like so:
		
	@media only screen and (max-device-width: 480px) {
		table[class=table], td[class=cell] { width: 300px !important; }
	   	table[class=promotable], td[class=promocell] { width: 325px !important; }
	}
	

####To avoid email not rendering background color throughout email in Yahoo! Mail, wrap the email in a `<div>` inside of the `<body>` tag. Set the background color of the email as a style on the div like so.

	<body bgcolor="#f1f1f1" topmargin="0" leftmargin="0" marginheight="0" marginwidth="0" style="-webkit-font-smoothing:antialiased;width:100% !important;background-color:#f1f1f1;">
		<div style="background-color: #f1f1f1; font-family: 'Helvetica', 'Arial', sans-serif; width: 100%;">

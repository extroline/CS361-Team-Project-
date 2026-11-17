## Dakota Rentz, Brendan Bessman, Zach Yarvis, Benny Garcia
# Client Questions 

## Format 
``` 
Question: What database is the tool list stored in?
Answer: Currently nothing.

Question: What database for the valid library card?
Answer: We have an API that can be called to check library card validity.

Question: Is there a website to checkout tools?
Answer: There is no existing website for the tool rentals. It will be different than the book website.

Question: Can you reserve those tools and go to a reserved pickup section in person?
Answer: Tools can be reserved on a wait list. There's no reserved tool pick up area. The borrower will have to pick it up off the shelf and bring it up to check out.

Question: What is the max number of tools someone can rent?
Answer: Borrowers can borrow up to five tools at once.

Question: Can you renew a tool?
Answer: Patrons can do a one-time renewal for the same timeframe as the original checkout.

Question: How are we determining fines for late/not returned equipment?
Answer: 1 day grace period (or until closing on the next open day): No fee. After that: $1/day for standard tools, $3/day for high-demand or large tools (tile saw, post-hole digger, pressure washer). Fees never exceed the tool's replacement value, or $20 per item, whichever is lower.

Question: How are we handling liability with these tools? Is there a waiver?
Answer: An electronic waiver needs to be kept for any tool rentals to happen. They should just do this once.

Question: How is each tool identified? Barcodes or asset tags per physical item, or per tool type?
Answer: We'll have an internal ID number for each, and we'd like them barcoded. We'd also like borrowers to be able to search and filter tools by category, availability, type, or name.

Question: Who handles maintenance, sharpening, battery charging, and replacement parts, and how often?
Answer: We'll want a way for any employees to note broken, missing, or damaged tools. The tools that aren't currently borrowed can be either "ready to borrow" or "in maintenance", so we should be able to flag them either way. Actual hands-on maintenance is handled by our staff.

Question: Do kits count as one item (e.g., drill + bits + case)? How do you verify all pieces are returned?
Answer: Kits count as a single item. Clerks will know to check the kits for all components upon return. Kits are labeled with their inventories.

Question: What's the plan for consumables (sandpaper, blades, bits)?
Answer: For simple consumables, the clerks can simply replace. For things requiring fixes, they can send them to our tech staff.

Question: Are minors allowed? Is there a minimum age?
Answer: Tools can only be borrowed by patrons 18 and over.

Question: Can one household member borrow on another's card?
Answer: Each borrower has to have their own card.

Question: What reports do you need (overdue, popular items, items in repair, usage by branch)?
Answer: We'd like to start with these reports: overdue, currently checked out, tools in repair, and most-borrowed.

Question: Do we want to offer classes for tools?
Answer: Not in this version.

Question: Do we want a kiosk system?
Answer: We'll have local computers just pointed at the website; all checkouts have to go through a librarian.

Question: Will it be first come first serve or reservations based maybe on a web system and an in person system?
Answer: Tools can be reserved on a wait list. Users on the wait list can cancel at any time and be taken off the wait list. Once they reach the front of the list, they have three days to pick up the tool, or the next person on the list moves to the front. We'll want it web-based. But we'll have local computers that people can access to check things out or reserve them. And a librarian should be able to reserve tools on someone's behalf if asked.

Question: What happens when tools aren't returned do we collect something to bill them with or is it just connected to their library account?
Answer: Unreturned tools just show up as maximum late fees (value of the tool) on the account. Borrowers can't borrow any more tools until the situation is rectified.

Question: If there is a reservation and a tool was returned inoperative will the future reservations be pushed back or the current one overwritten?
Answer: The system should be built so that clerks can note if a tool needs servicing. They should be able to describe what needs to be done and mark the tool as "out of service". This doesn't affect the wait list; they just have to wait until the tool is marked "in service" before they are allowed to borrow again.

Question: Does the existing API provide patron age and account standing or only card validity? If only validity, should we have everyone create a new account with age verification process? 
Answer: The API also has provided metadata about the borrower. In any case, we check age when we checkout because you need an ID to borrow. 

Question: How should conflicts be handled when someone is on the tool waitlist and the person currently using it wants to renew it? 
Answer: Borrowers cannot renew if there is anyone on the waitlist. 

Question: How long do we wait until we list a tool as unreturned? 
Answer: Tools not returned beyond the due date are immediately marked as unreturned. 

Question: Is the lost tool charge separate from the $20 overdue fee cap? 
Answer: No—the late fee cap is it. 

Question: Does the client want a borrower to have a personal dashboard or just a checkout process? 
Answer: A dashboard showing the rental history and status would be great (how many days left on the loan, fees, etc.)
``` 

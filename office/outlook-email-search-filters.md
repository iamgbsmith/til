# Outlook Email Search Filters

__Category: Office__

You can search and filter messages/emails, calendar events, tasks, and contacts in Outlook. 

Searches are typically run against folders by typing a value into the `Search` input field. If a search predicate is omitted, the search criteria will include the subject body and sender.

The following searches can be used against emails.


| Filter                | Filter functionality   |
| --------------------- |----------------------- | 
| `isread:no`               | Unread emails |
| `from:steve@orbiks.com`   | Emails from a sender based on email address |
| `from:"james watson"`     | Emails from a sender matching a name        |
| `messagesize:> 2MB`       | Emails larger than a specific size (can be `KB` or `MB`)    |
| `received:today`          | Emails from today (can also specify `yesterday`, `"this week"` or `"last week"`) |
| `received:1/24/2022`      | Emails received on a specific date |
| `subject:"azure devops"`  | Emails matching a subject keyword |
| `hasattachment:yes`       | Emails with attachments |

__Note:__ Searches using string literals are case-insensitive.

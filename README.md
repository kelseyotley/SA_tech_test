# Reports for Non-Users 
## (Ex: Front of House)
### Background:
With our New Verticals accounts, there are commonly front of house staff who won’t have any internal access or usage of Klaviyo but have requested insight into reporting for channel conversions to their store.  Currently for a user to get a custom report they have to sign in under their user and schedule their reports to their inboxes. However, the report that gets sent into the inbox navigates back into the klaviyo account (preventing any forwarding to work for non-users). Therefore, there is no easy way to automate reports to non-users.

As a first step, this solution will allow users to query the count and sum of key events in their Klaviyo account on a daily, weekly, or monthly basis. After pulling the aggregates, users will transform them into a net new event into Klaviyo. This event will be attached to a static profile to be used as the conduit to a metric triggered flow that sends an internal note with the aggregate sums/counts from that day, week or month to any email.

### Solution:
1. Query Metric Aggregates from key KPIs
2. Transform query into new Reporting Event
3. Set up flow triggered from weekly Reporting Event with appropriate Internal Note
4. Personalize Internal Note with event variables from the week

### To Get Started:
1. Download or clone the repository from Github
2. Create a Klaviyo Account
3. Confirm Conversion metrics in account
4. Create/determine klaviyo profile (email address will act as conduit to trigger the Weekly Report Flow)
5. Replace the following variables in your script:
##### Variable:
      a. "my_secret" - this is your private API key. You can create in Klaviyo > Accounts > Settings > API keys. Then input as a secret in Replit.

##### GetBookingPayload:
      a. "measurements" - choose preference for reporting measurements (ex: counts, sum_value)
      b. "filter" - datetime period you are reporting on
      c. "metric_id" - conversion metric you need to report on
      d. "interval" - daily, weekly, monthly (depending on reporting frequency)
      e. "timezone" - timezone of account
      f. "revision" - make sure you are using up-to-date revision

##### WeeklyReportPayload:
      a. "email" - email of klaviyo profile being used as conduit for report flow
      b. "id" - id of klaviyo profile being used as conduit for report flow (can be found in URL when on profile page)

### Expanded Implications for New Verticals:

While this is a basic version of reporting to non-users (just count and sum of a single metric from the past week), ideally this solution would expand to be a source of communication  to front of house staff based on events in Klaviyo. The conversion metric can be expanded from Booked Appointments to additional/other events like completed appointments, canceled appointments, etc, to get a better understanding on weekly, monthly or daily activity straight out of the klaviyo platform.

Additionally, this could ideally be used for something like predictive reporting to send an email to front of staff if there is a large influx of bookings or cancellations to be able to accommodate for staffing adjustments.

As Klaviyo opens doors wider for New Verticals, we are coming up against use cases not solved for innately in our toolbox. I can see this reporting to non-users coming up much more frequently as a request to restaurants, salons and spas that have brick and mortar stores.


### Case Study:

Replit Script:
https://replit.com/join/zzmwpjapbz-kelseyotley 

Example Profile as conduit to report:
https://www.klaviyo.com/profile/01G784FY21D0SE17GJCAEZGZ99

Example flow with internal note sending out basic report:
https://www.klaviyo.com/flow/Yx8ceL/edit

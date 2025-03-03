# New

Delete this text and replace it with your own content. @Snippet:Auditor:Review_the_following@
        
- <madcap:xref href="#To_create_a_subscription" class="Just_link"><u><span style="color: #2a5d89;" class="mcFormatColor">To create a subscription</span></u>
                </madcap:xref>
- <madcap:xref href="#To_manage_subscriptions" class="Just_link"><u><span style="color: #2a5d89;" class="mcFormatColor">To manage subscriptions</span></u>
                </madcap:xref>

To create a subscription

1. Do one of the following:
    - On the main {{ MyVariables.ProductName }} page, navigate to Reports. Specify the report that you want to subscribe to and click Subscribe.
    - On the main {{ MyVariables.ProductName }} page, navigate to Enterprise Overview. Specify the audited system, whose report you want to subscribe to and click Subscribe.
2. On the Subscribe to the 'report\_name' report page, complete the following fields:

    | Option | Description |
    | --- | --- |
    | Subscription name | Enter the name for the subscription. |
    | Delivery format | Configure reports to be delivered as the pdf, docx, csv or xlsx files. |
    | Send empty reports | Select Yes if you want to receive a report even if no changes occurred.<br><ul madcap:conditions="Auditor/2_Output.Hidden">
<br>                                    <li><span style="font-family: 'Open Sans Semibold';">Do not send empty reports</span>—Select this option if you do not want reports to be generated when no changes occurred during the reporting period. </li>
<br>                                    <li><span style="font-family: 'Open Sans Semibold';">Allow sending empty report</span>—Select this option if you want to receive empty reports anyway. </li>
<br>                                </ul> |
    | Deliver report to... | Shows the number of recipients selected and allows specifying emails where reports are to be sent. <br>
<br>                                <br>Expand the Recipients list and click Add to add more recipients. |
    | Every... | Allows specifying report delivery schedule (daily, certain days of week, a certain day of a certain month). <br>
<br>                                <br>By default, the product emails reports daily at 8.00 am. |
    | Attach report to email / Upload report to file server | Select report delivery method:<br><ul>
<br>                                    <li><span style="font-family: 'Open Sans Semibold';">Attach report to email</span>—Select this option to receive reports as email attachments. </li>
<br>                                    <li>
<br>                                        <p><span style="font-family: 'Open Sans Semibold';">Upload report to file server</span>—Select this option to save reports on the selected file server. Click <span style="font-family: 'Open Sans Semibold';">Browse</span> to select a folder on Netwrix Auditor host (computer where {{ MyVariables.NAC }} is installed) or specify a UNC path to a shared network resource.</p>
<br>                                        <p class="Note" madcap:autonum="&lt;b&gt;&lt;span style=&quot;color: #1560ce;&quot; class=&quot;mcFormatColor&quot;&gt;NOTE: &lt;/span&gt;&lt;/b&gt;">Make sure that your network resource is reachable and you have sufficient rights to access it.</p>
<br>                                    </li>
<br>                                </ul> |
    | Filters | Specify the report filters, which vary depending on the selected report. |

    Subscription emails may vary slightly depending on reports delivery method.![](../../Images/Audit_Intel/AI_Subscriptions_Email.PNG)

To manage subscriptions

- On the main {{ MyVariables.ProductName }} page, navigate to Subscriptions to review a list of your subscriptions.![](../../Images/Audit_Intel/AI_Subscribe_Wizard.PNG)

The table below provides instructions on how to manage your subscriptions.

| To... | Do... |
| --- | --- |
| Browse subscriptions | Type the target subscription name in the search bar in the upper part of the Subscriptions window and click the Search icon to review results. |
| Enable or disable subscriptions | Select a subscription  and check or clear the Enabled checkbox in the Status column. |
| Modify subscriptions | Click![](../../Images/Audit_Intel/edit_subscription.PNG) icon next to the selected subscription. Edit the subscription parameters and save your changes. |
| Remove subscriptions | Click![](../../Images/Audit_Intel/Delete.PNG) icon next to the selected subscription. |
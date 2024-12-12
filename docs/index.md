
    <!DOCTYPE html>
    <html>
    <head>
        <title>Django Template Variables Documentation</title>
        <style>
            .expandable-section {
                margin: 10px 0;
                padding: 10px;
                border: 1px solid #ddd;
                border-radius: 4px;
            }
            .expandable-section summary {
                cursor: pointer;
                padding: 5px;
            }
            table {
                border-collapse: collapse;
                width: 100%;
                margin: 15px 0;
            }
            th, td {
                border: 1px solid #ddd;
                padding: 8px;
                text-align: left;
            }
            th {
                background-color: #f5f5f5;
            }
            code {
                background-color: #f5f5f5;
                padding: 2px 4px;
                border-radius: 3px;
            }
        </style>
    </head>
    <body>

    # Django Template Variables Documentation

## Note on Variable Names

Some variables appear in templates under different forms. The documentation consolidates these under canonical names:

- `lineitem_group` (also appears as: `lineitems`, `lineitem`)
- `invoices` (also appears as: `invoice`)
- `consolidated_tasks` (also appears as: `config`)

---

## accreditation

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>name</code></td><td>{{accreditation.name}}</td></tr>
<tr><td><code>number</code></td><td>{{ accreditation.number }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<td>
{% for accreditation in technician.accreditations %}
<div>{{accreditation.name}}: {{ accreditation.number }}</div>
{% endfor %}
</td>

```

</details>


</body>
</html>## after_photos

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<strong>After</strong>
<div class="...">
{% for photo in after_photos %}
{% include "webtemplates/2022-photo-tile" with photo=photo class="..." %}
{% endfor %}

```

</details>


</body>
</html>## appointments

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Appointment Scheduled Email](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>scheduled_start</code></td><td>{{appointments.scheduled_start}}</td></tr>
<tr><td><code>task</code></td><td>{{appointments.task.property.name}}</td></tr>
<tr><td><code>task.name</code></td><td>{{appointments.task.name}}</td></tr>
<tr><td><code>task.property</code></td><td>{{appointments.task.property.name}}</td></tr>
<tr><td><code>task.property.name</code></td><td>{{appointments.task.property.name}}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

{% timezone appt.timezone %}
<tr>
<th style="..." scope="..." colspan="...">{{appt.scheduled_start}}</th>
<td style="...">{{appt.task.name}}</td>
<td style="...">{{appt.task.property.name}}</td>

```

</details>


---

```django

<tr>
<th style="..." scope="..." colspan="...">{{appt.scheduled_start}}</th>
<td style="...">{{appt.task.name}}</td>
<td style="...">{{appt.task.property.name}}</td>
</tr>

```

</details>


</body>
</html>## attention

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Defect Quote Summary Reminder Email](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Issuance](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Service Quote Issued Email](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

{% load getattr %}
{% block content %}
<p>Dear {{ attention|default:"Manager" }},</p>
<p>You have been selected as the main recipient or a CC in this repeating reminder.</p>
<p>We are waiting for approval for the following defect quotes:</p>

```

</details>


---

```django

<p>
Dear {{ attention|default:'valued customer' }},
</p>
<p>

```

</details>


</body>
</html>## base_url

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Monthly Uncovered Assets](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<ul>
{% for property in properties %}
<li><a href="{{base_url}}/properties/{{property.property_id}}/view/assets/?is_covered_by_routine=False&is_active=True">{{ property.property__name }}</a></li>
{% endfor %}
</ul>

```

</details>


</body>
</html>## before_photos

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

{% endif %}
<div class="...">
{% for photo in before_photos %}
{% include "webtemplates/2022-photo-tile" with photo=photo class="..." %}
{% endfor %}

```

</details>


</body>
</html>## client

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Service Quote Reminder Email](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>name</code></td><td>{{ client.name|default:'valued customer' }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<p>Dear {{ client.name|default:'valued customer' }},</p>
<p>This is a friendly reminder that we’re awaiting your quote approval for {{ property }}.</p>
{% if servicequote.description %}

```

</details>


</body>
</html>## consolidated_tasks

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Consolidated Invoice](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Invoice](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Service Quote (Totals only)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>COMPANY_LICENSES</code></td><td>{{ consolidated_tasks.COMPANY_LICENSES|markdowner }}</td></tr>
<tr><td><code>INVOICE_PAYMENT_INSTRUCTIONS</code></td><td>{{ consolidated_tasks.INVOICE_PAYMENT_INSTRUCTIONS|markdowner|default:"Please pay invoice by the due date" }}</td></tr>
<tr><td><code>SERVICEQUOTE_TEMPLATE_TERMS_AND_CONDITIONS</code></td><td>{{ consolidated_tasks.SERVICEQUOTE_TEMPLATE_TERMS_AND_CONDITIONS|markdowner }}</td></tr>
<tr><td><code>SITE_ABN</code></td><td>{{ consolidated_tasks.SITE_ABN }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<small>
<strong class="...">Company Accreditations:</strong>
<div class="...">{{ config.COMPANY_LICENSES|markdowner }}</div>
</small>
</section>

```

</details>


---

```django

<p>{{ config.SITE_ABN }}</p>
<h6>Payment instructions</h6>
{{ config.INVOICE_PAYMENT_INSTRUCTIONS|markdowner|default:"Please pay invoice by the due date" }}
</section>
{% endblock %}

```

</details>


</body>
</html>## creditnotes

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Consolidated Invoice](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>number</code></td><td>{{ note.number }}</td></tr>
<tr><td><code>total</code></td><td>{{ note.total|currency }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

</tr>
{% if creditnotes %}
{% for note in creditnotes %}
<tr>
<th class="...">Credit {{ note.number }} - {{ note }}</th>

```

</details>


</body>
</html>## defectquotes

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Issuance](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>get_uuid_approval_url</code></td><td>{{ quote.get_uuid_approval_url }}</td></tr>
<tr><td><code>ref</code></td><td>{{ quote.ref }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<p>Your defect quotes:</p>
<ul>
{% for quote in defectquotes %}
<li>Reference: {{ quote.ref }}<a href="{{ base_url }}{{ quote.get_uuid_approval_url }}"> (approve online)</a></li>
{% endfor %}

```

</details>


</body>
</html>## digital_logbooks

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [emails] - [Issuance](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>name</code></td><td>{{ logbook.name }}</td></tr>
<tr><td><code>url</code></td><td>{{ entry.url }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

</div>
{% endfor %}
{% for entry in digital_logbooks %}
<div class="...">
<div class="...">

```

</details>


---

```django

<p>Your attached digital logbook entries:</p>
<ul>
{% for logbook in digital_logbooks %}
<li>{{ logbook.name }}</li>
{% endfor %}

```

</details>


</body>
</html>## doandchargelineitems

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Quote (Routines)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Service Quote (Totals only)](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

</thead>
<tbody>
{% for line in doandchargelineitems %}
<tr class="...">
<td>

```

</details>


</body>
</html>## email

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Defect Quote Summary Reminder Email](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

{% for email in quote_email_lookup|getvalue:quote %}
{% if email != recipient %}
<li>{{email}}</li>
{% endif %}
{% endfor %}

```

</details>


</body>
</html>## entry

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>files</code></td><td>{% for file in entry.files %}</td></tr>
<tr><td><code>logbook</code></td><td>{{ entry.logbook.name|default:'-' }}</td></tr>
<tr><td><code>logbook.name</code></td><td>{{ entry.logbook.name|default:'-' }}</td></tr>
<tr><td><code>preview_url</code></td><td>{{ file.preview_url }}</td></tr>
<tr><td><code>url</code></td><td>{{ entry.url }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<div class="...">
<a href="{{ entry.url }}">
<strong>{{ entry.logbook.name|default:'-' }}</strong>
{% include "reports/library/arrow-up-right-from-square-icon.svg" with width="..." height="..." %}
</a>

```

</details>


---

```django

<div class="...">
<strong>{{ entry.logbook.name|default:'-' }}</strong>
{% for file in entry.files %}
<a class="..." href="{{ file.preview_url }}">
{% include "reports/library/arrow-up-right-from-square-icon.svg" with width="..." height="..." %}

```

</details>


</body>
</html>## fixedlineitems

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Quote (Totals only)](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

</thead>
<tbody>
{% for line in fixedlineitems %}
<tr class="...">
<td>

```

</details>


</body>
</html>## formresponses

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Issuance](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

{% endif %}
<ul>
{% for formresponse in formresponses %}
<li>{{ formresponse }}</li>
{% endfor %}

```

</details>


</body>
</html>## invoices

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Consolidated Invoice](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Invoice](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [emails] - [Issuance](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Overdue Invoice Reminder Email](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>billingcard</code></td><td>{{ invoices.billingcard.postal_address|linebreaksbr }}</td></tr>
<tr><td><code>billingcard.postal_address</code></td><td>{{ invoices.billingcard.postal_address|linebreaksbr }}</td></tr>
<tr><td><code>date</code></td><td>{{ invoices.date|date:"jS F Y"|default:"-" }}</td></tr>
<tr><td><code>description</code></td><td>{{ invoices.description|markdowner }}</td></tr>
<tr><td><code>due_date</code></td><td>{{ invoices.due_date|date:"jS F Y" }}</td></tr>
<tr><td><code>gst</code></td><td>{{ invoices.gst|currency }}</td></tr>
<tr><td><code>number</code></td><td>{{ invoices.number|default:"-" }}</td></tr>
<tr><td><code>ref</code></td><td>{{ inv.ref }}</td></tr>
<tr><td><code>subtotal</code></td><td>{{ invoices.subtotal|currency }}</td></tr>
<tr><td><code>total</code></td><td>{{ invoices.total|currency }}</td></tr>
<tr><td><code>total_after_credits</code></td><td>{{ invoices.total_after_credits|currency }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<p>Your invoice:</p>
<ul>
<li>{{ invoice.number|default:"[[ invoice_number ]]" }} {% if invoice.ref %}({{ invoice.ref }}){% endif %}</li>
</ul>
{% endif %}

```

</details>


---

```django

Number: {{ inv.number }}<br>
Reference: {{ inv.ref }}<br>
Due: {{ inv.due_date|date:"jS F Y" }}<br>
{% endfor %}
For any questions please contact the office.</p>

```

</details>


</body>
</html>## items

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Signoff Disclaimed](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>label</code></td><td>{{ item.label }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<p>We have received notification from {{ contractor.name }} that they are no longer engaged to maintain the following items:</p>
<ul>
{% for item in items %}
<li>{{ item.label }}</li>
{% endfor %}

```

</details>


</body>
</html>## joyfillformresponses

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [emails] - [Issuance](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

{% endif %}
<ul>
{% for formresponse in joyfillformresponses %}
<li>{{ formresponse }}</li>
{% endfor %}

```

</details>


</body>
</html>## labour_sessions

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>finished</code></td><td>{{ tasksession.finished|timezone:tasksession.timezone|date:'H:i'|default:"(still in progress)" }}</td></tr>
<tr><td><code>get_duration</code></td><td>{{ tasksession.get_duration|duration }}</td></tr>
<tr><td><code>get_type_display</code></td><td>{{ tasksession.get_type_display }}</td></tr>
<tr><td><code>started</code></td><td>{{ tasksession.started|timezone:tasksession.timezone|date:'d/m/Y H:i' }}</td></tr>
<tr><td><code>technician</code></td><td>{{ tasksession.technician }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

</thead>
<tbody>
{% for tasksession in labour_sessions %}
<tr>
<td>{{ tasksession.get_type_display }}</td>

```

</details>


</body>
</html>## lineitem_group

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Consolidated Invoice](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Invoice](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Itemised w Prices	](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Itemised w Qty	](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Purchase Order](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Service Quote (Routines)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Service Quote (Totals only)](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>annual_subtotal</code></td><td>{{ lineitem_group.annual_subtotal|currency }}</td></tr>
<tr><td><code>asset</code></td><td>{{ lineitem_group.asset.get_label|default:"General Repairs" }}</td></tr>
<tr><td><code>asset.get_label</code></td><td>{{ lineitem_group.asset.get_label|default:"General Repairs" }}</td></tr>
<tr><td><code>cost_summary</code></td><td>{{ lineitem_group.cost_summary.total|currency }}</td></tr>
<tr><td><code>cost_summary.gst</code></td><td>{{ lineitem_group.cost_summary.gst|currency }}</td></tr>
<tr><td><code>cost_summary.subtotal</code></td><td>{{ lineitem_group.cost_summary.subtotal|currency }}</td></tr>
<tr><td><code>cost_summary.total</code></td><td>{{ lineitem_group.cost_summary.total|currency }}</td></tr>
<tr><td><code>description</code></td><td>{{ lineitem_group.description|default:'-' }}</td></tr>
<tr><td><code>gst</code></td><td>{{ lineitem_group.gst|currency }}</td></tr>
<tr><td><code>lineitems</code></td><td>{% for lineitem in lineitem_group.lineitems %}</td></tr>
<tr><td><code>name</code></td><td>{{ rslt.name }}</td></tr>
<tr><td><code>property</code></td><td>{{ lineitem_group.property.client_ref}}</td></tr>
<tr><td><code>property.client_ref</code></td><td>{{ lineitem_group.property.client_ref}}</td></tr>
<tr><td><code>quantity</code></td><td>{{ lineitem.quantity|floatformat:2 }}</td></tr>
<tr><td><code>remark</code></td><td>{{ lineitem_group.remark.get_description|markdowner }}</td></tr>
<tr><td><code>remark.get_description</code></td><td>{{ lineitem_group.remark.get_description|markdowner }}</td></tr>
<tr><td><code>remark.get_public_url</code></td><td>{{ lineitem_group.remark.get_public_url|absolute }}</td></tr>
<tr><td><code>remark.get_resolution</code></td><td>{{ lineitem_group.remark.get_resolution|markdowner }}</td></tr>
<tr><td><code>remark.location</code></td><td>{{ lineitem_group.remark.location|markdowner }}</td></tr>
<tr><td><code>routineserviceleveltypes</code></td><td>{% for rslt in lineitem_group.routineserviceleveltypes.all %}</td></tr>
<tr><td><code>routineserviceleveltypes.all</code></td><td>{% for rslt in lineitem_group.routineserviceleveltypes.all %}</td></tr>
<tr><td><code>site_price</code></td><td>{{ lineitem_group.site_price|currency }}</td></tr>
<tr><td><code>subtotal</code></td><td>{{ lineitem_group.subtotal|currency }}</td></tr>
<tr><td><code>task</code></td><td>{{ lineitem_group.task.invoice_note|markdowner }}</td></tr>
<tr><td><code>task.description</code></td><td>{{ lineitem_group.task.description|markdowner }}</td></tr>
<tr><td><code>task.invoice_note</code></td><td>{{ lineitem_group.task.invoice_note|markdowner }}</td></tr>
<tr><td><code>task.scope_of_works</code></td><td>{{ lineitem_group.task.scope_of_works|markdowner }}</td></tr>
<tr><td><code>unit_price</code></td><td>{{ lineitem.unit_price|currency }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<td colspan="...">
<div>
<strong>{{ lineitem.asset.get_label|default:"General Repairs" }}</strong>
<div>{{ lineitem.asset.location }}</div>
</div>

```

</details>


---

```django

<strong>{{ lineitem.remark.get_severity_display }}</strong>
<div>
<a href="{{ lineitem.remark.get_public_url|absolute }}">
ID: {{ lineitem.remark.id }}
{% include "reports/library/arrow-up-right-from-square-icon.svg" with width="..." height="..." %}

```

</details>


</body>
</html>## maintenance_technicians

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>asset</code></td><td>{{ row.asset }}</td></tr>
<tr><td><code>count</code></td><td>{{ row.count }}</td></tr>
<tr><td><code>inspected_date</code></td><td>{{ technician.inspected_date }}</td></tr>
<tr><td><code>name</code></td><td>{{ technician.name }}</td></tr>
<tr><td><code>service</code></td><td>{{ row.service }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

</thead>
<tbody>
{% for row in maintenance_summary %}
<tr>
<td>{{ row.service }}</td>

```

</details>


---

```django

</thead>
<tbody>
{% for technician in maintenance_technicians %}
<tr>
<td>{{ technician.name }}</td>

```

</details>


</body>
</html>## note

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Consolidated Invoice](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>number</code></td><td>{{ note.number }}</td></tr>
<tr><td><code>total</code></td><td>{{ note.total|currency }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<tr>
<th class="...">Credit {{ note.number }} - {{ note }}</th>
<td class="...">{{ note.total|currency }}</td>
</tr>
{% endfor %}

```

</details>


</body>
</html>## paper_logbooks

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [emails] - [Corrigo Webhook Event Rejection](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<div class="...">Logbooks</div>
<div class="...">
{% for entry in paper_logbooks %}
<div class="...">
<div class="...">

```

</details>


---

```django

<p>Reason: {{ message }}</p>
<p>Payload:<p>
<pre><code>{{payload}}</code></pre>
<p>Regards,<br >Uptick Team</p>

```

</details>


</body>
</html>## photos

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Itemised w Prices	](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Itemised w Qty	](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

{% if photos %}
<div class="...">
{% for photo in photos %}
{% include "webtemplates/2022-photo-tile" with photo=photo class="..." %}
{% endfor %}

```

</details>


</body>
</html>## productlineitems

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Quote (Routines)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Service Quote (Totals only)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [emails] - [Monthly Uncovered Assets](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Signoff Generation Notification Email](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>description</code></td><td>{{ line.description|default:'-' }}</td></tr>
<tr><td><code>property__name</code></td><td>{{ productlineitems.productlineitems__name }}</td></tr>
<tr><td><code>property_id</code></td><td>{{productlineitems.productlineitems_id}}</td></tr>
<tr><td><code>quantity</code></td><td>{{ line.quantity|floatformat:2 }}</td></tr>
<tr><td><code>subtotal</code></td><td>{{ line.subtotal|currency }}</td></tr>
<tr><td><code>unit_price</code></td><td>{{ line.unit_price|currency }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<ul>
{% for property in properties %}
<li><a href="{{base_url}}/properties/{{property.property_id}}/view/assets/?is_covered_by_routine=False&is_active=True">{{ property.property__name }}</a></li>
{% endfor %}
</ul>

```

</details>


---

```django

<p>There are currently {{ no_of_assets }} assets not covered by any Routines. These assets relate to the following properties:</p>
<ul>
{% for property in properties %}
<li><a href="{{base_url}}/properties/{{property.property_id}}/view/assets/?is_covered_by_routine=False&is_active=True">{{ property.property__name }}</a></li>
{% endfor %}

```

</details>


</body>
</html>## purchaseorder

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Purchase Order](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>created</code></td><td>{{ purchaseorder.created|date:"jS F Y" }}</td></tr>
<tr><td><code>currency</code></td><td>{{ purchaseorder.currency }}</td></tr>
<tr><td><code>delivery_instructions</code></td><td>{{ purchaseorder.delivery_instructions|markdowner }}</td></tr>
<tr><td><code>description</code></td><td>{{ purchaseorder.description|markdowner }}</td></tr>
<tr><td><code>gst</code></td><td>{{ purchaseorder.gst|currency }}</td></tr>
<tr><td><code>subtotal</code></td><td>{{ purchaseorder.subtotal|currency }}</td></tr>
<tr><td><code>total</code></td><td>{{ purchaseorder.total|currency }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<div class="...">
<div class="...">
{{ purchaseorder.description|markdowner }}
{% if purchaseorder.delivery_instructions %}
<dl>

```

</details>


---

```django

<dl>
<dt>Delivery instructions</dt>
<dd>{{ purchaseorder.delivery_instructions|markdowner }}</dd>
</dl>
{% endif %}

```

</details>


</body>
</html>## quotes

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Itemised w Prices	](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Itemised w Qty	](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [emails] - [Defect Quote Summary Reminder Email](https://AARHUSFIRE.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>get_uuid_approval_url</code></td><td>{{ quote.get_uuid_approval_url }}</td></tr>
<tr><td><code>gst</code></td><td>{{quotes.gst|currency}}</td></tr>
<tr><td><code>ref</code></td><td>{{ quote.ref }}</td></tr>
<tr><td><code>subtotal</code></td><td>{{quotes.subtotal|currency}}</td></tr>
<tr><td><code>total</code></td><td>{{quotes.total|currency}}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<p>You have been selected as the main recipient or a CC in this repeating reminder.</p>
<p>We are waiting for approval for the following defect quotes:</p>
{% for quote in quotes %}
<p>
<div>Reference: {{ quote.ref }}</div>

```

</details>


---

```django

<tr>
<td width="..." class="..."><strong>Subtotal </strong></td>
<td width="...">{{quote.subtotal|currency}}</td>
</tr>
<tr>

```

</details>


</body>
</html>## rectification

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [emails] - [Appointment Scheduled Email](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Issuance](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Overdue Invoice Reminder Email](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Rectification Rejected](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>asset</code></td><td>{{ rectification.asset.get_label|default:"General Repairs" }}</td></tr>
<tr><td><code>asset.get_label</code></td><td>{{ rectification.asset.get_label|default:"General Repairs" }}</td></tr>
<tr><td><code>compliant</code></td><td>{{ rectification.compliant|yesno:"compliant,non-compliant,not applicable"}}</td></tr>
<tr><td><code>email</code></td><td>{{rectification.email}}</td></tr>
<tr><td><code>get_title</code></td><td>{{ report.get_title }}</td></tr>
<tr><td><code>name</code></td><td>{{rectification.name}}</td></tr>
<tr><td><code>notes</code></td><td>{{ rectification.notes|default:rectification.product.description|default:rectification.product.name }}</td></tr>
<tr><td><code>quantity</code></td><td>{{ rectification.quantity|floatformat:2 }}</td></tr>
<tr><td><code>ref</code></td><td>{{ rectification.ref }}</td></tr>
<tr><td><code>rejection_reason</code></td><td>{{ rectification.rejection_reason|markdowner }}</td></tr>
<tr><td><code>remark</code></td><td>{{ rectification.remark.get_description|markdowner }}</td></tr>
<tr><td><code>remark.get_description</code></td><td>{{ rectification.remark.get_description|markdowner }}</td></tr>
<tr><td><code>remark.get_public_url</code></td><td>{{ rectification.remark.get_public_url|absolute }}</td></tr>
<tr><td><code>remark.get_resolution</code></td><td>{{ rectification.remark.get_resolution|markdowner }}</td></tr>
<tr><td><code>remark.location</code></td><td>{{ rectification.remark.location|markdowner }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<tr class="...">
<td colspan="...">
<strong>{{ repair.asset.get_label|default:"General Repairs" }}</strong>
<div>{{ repair.asset.location }}</div>
</td>

```

</details>


---

```django

<strong>{{ repair.remark.get_severity_display }}</strong>
<div>
<a href="{{ repair.remark.get_public_url|absolute }}">
ID: {{ repair.remark.id }}
{% include "reports/library/arrow-up-right-from-square-icon.svg" with width="..." height="..." %}

```

</details>


</body>
</html>## servicelineitems

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Quote (Routines)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Service Quote (Totals only)](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>annual_gst</code></td><td>{{ servicelineitems.annual_gst|currency }}</td></tr>
<tr><td><code>annual_subtotal</code></td><td>{{ servicelineitems.annual_subtotal|currency }}</td></tr>
<tr><td><code>annual_tax</code></td><td>{{ servicelineitems.annual_tax|currency }}</td></tr>
<tr><td><code>annual_total</code></td><td>{{ servicelineitems.annual_total|currency }}</td></tr>
<tr><td><code>created</code></td><td>{{ servicelineitems.created|date:"jS F Y" }}</td></tr>
<tr><td><code>expiry_date</code></td><td>{{ servicelineitems.expiry_date }}</td></tr>
<tr><td><code>product_gst</code></td><td>{{ servicelineitems.product_gst|currency }}</td></tr>
<tr><td><code>product_subtotal</code></td><td>{{ servicelineitems.product_subtotal|currency }}</td></tr>
<tr><td><code>product_total</code></td><td>{{ servicelineitems.product_total|currency }}</td></tr>
<tr><td><code>ref</code></td><td>{{ servicelineitems.ref }}</td></tr>
<tr><td><code>scope_of_works</code></td><td>{{ servicelineitems.scope_of_works|markdowner }}</td></tr>
<tr><td><code>terms_and_conditions</code></td><td>{{ servicelineitems.terms_and_conditions|markdowner }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<section class="...">
<h2 class="...">Service Quotation <strong>{{ servicequote.ref }}</strong></h2>
<div>{{ servicequote.created|date:"jS F Y" }}</div>
{% if servicequote.expiry_date %}<div>This quote is valid until <em>{{ servicequote.expiry_date }}</em></div>{% endif %}
<div><strong>Attention: {{ client.primary_contact.name }}</strong></div>

```

</details>


---

```django

{% if servicequote.scope_of_works %}
<div class="...">
{{ servicequote.scope_of_works|markdowner }}
</div>
{% endif %}

```

</details>


</body>
</html>## show_rate_column

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Purchase Order](https://AARHUSFIRE.onuptick.com/configuration/templates)

</details>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<th class="..." width="...">Unit Price</th>
<th class="..." width="...">Subtotal</th>
<th class="..." width="..."100,0" }}">
{% if show_rate_column %}{% get_tax_summary_name %} Rate{% endif %}
</th>

```

</details>


</body>
</html>## signoffproperties

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [emails] - [Signoff Disclaimed](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Signoff Reminder](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Signoff Request](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Signoff Response](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>account</code></td><td>{{ signoffproperties.account }}</td></tr>
<tr><td><code>contractor</code></td><td>{{ signoffproperties.contractor }}</td></tr>
<tr><td><code>created</code></td><td>{{ signoffproperty.created|date }}</td></tr>
<tr><td><code>disclaimed_reason</code></td><td>{{signoffproperties.disclaimed_reason}}</td></tr>
<tr><td><code>due</code></td><td>{{ signoffproperty.due|date }}</td></tr>
<tr><td><code>filename</code></td><td>{{ signature.filename }}</td></tr>
<tr><td><code>is_disclaimed</code></td><td>{{ signoffproperties.is_disclaimed|yesno:"red,black" }}</td></tr>
<tr><td><code>label</code></td><td>{{ signoffitem.label }}</td></tr>
<tr><td><code>new_is_compliant</code></td><td>{{ signoffitem.new_is_compliant|yesno:"green,red" }}</td></tr>
<tr><td><code>new_serviced_date</code></td><td>{{ signoffitem.new_serviced_date }}</td></tr>
<tr><td><code>new_signoff_note</code></td><td>{{ signoffitem.new_signoff_note }}</td></tr>
<tr><td><code>note</code></td><td>{{ signoffproperties.note }}</td></tr>
<tr><td><code>period_finish</code></td><td>{{ signoffproperties.period_finish }}</td></tr>
<tr><td><code>period_start</code></td><td>{{ signoffproperties.period_start}}</td></tr>
<tr><td><code>pk</code></td><td>{{ signoffproperties.pk }}</td></tr>
<tr><td><code>property</code></td><td>{{ signoffproperties.property }}</td></tr>
<tr><td><code>signoffitem_set</code></td><td>{% for signoffitem in signoffproperties.signoffitem_set.all %}</td></tr>
<tr><td><code>signoffitem_set.all</code></td><td>{% for signoffitem in signoffproperties.signoffitem_set.all %}</td></tr>
<tr><td><code>signoffproperty_set</code></td><td>{% for signoffpropertiesproperty in signoffproperties.signoffpropertiesproperty_set.all %}</td></tr>
<tr><td><code>signoffproperty_set.all</code></td><td>{% for signoffpropertiesproperty in signoffproperties.signoffpropertiesproperty_set.all %}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<div class="...">Signatures</div>
<div class="...">
{% for signature in signatures %}
<div class="...">
<div class="...">{% cdn_image signature.path height=100 crop="fill" type="authenticated" %}</div>

```

</details>


---

```django

{% extends 'email.html' %}
{% block content %}
<h4>Request{{ signoffproperties|pluralize }} for {{ contractor.name }} ({{ contractor.account }}).</h4>
<p>In order to issue compliant reports, we require confirmation that you, as a service contractor, have serviced the relevant Essential Safety Measures to Australian Standards over the previous 12 months.</p>
<table border="..." cellpadding="..." cellspacing="..." bgcolor="..." width="...">

```

</details>


</body>
</html>## summary_remarks

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Itemised w Prices	](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Itemised w Qty	](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>0</code></td><td>{{ summary_remarks.0|default:"0" }}</td></tr>
<tr><td><code>1</code></td><td>{{ summary_remarks.1|default:"0" }}</td></tr>
<tr><td><code>10</code></td><td>{{ summary_remarks.10|default:"0" }}</td></tr>
<tr><td><code>2</code></td><td>{{ summary_remarks.2|default:"0" }}</td></tr>
<tr><td><code>5</code></td><td>{{ summary_remarks.5|default:"0" }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<tbody>
<tr>
<td width="..." class="..."><strong>{{ summary_remarks.10|default:"0" }}</strong></td>
<td width="..." class="..."><strong>Critical Defects</strong></td>
<td width="..." class="...">A defect that renders a system inoperative.</td>

```

</details>


---

```django

</tr>
<tr>
<td class="..."><strong>{{ summary_remarks.5|default:"0" }}</strong></td>
<td class="..."><strong>Non-critical Defects</strong></td>
<td class="...">A system impairment not likely to critically affect the operation of the system.</td>

```

</details>


</body>
</html>## task_origin_defectquote

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [AARHUSFIRE] - [emails] - [Bulk Contractor Contact Task Assignment Email](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [AARHUSFIRE] - [emails] - [Task Assigned Email](https://AARHUSFIRE.onuptick.com/configuration/emails)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>address</code></td><td>{{ task.address }}</td></tr>
<tr><td><code>description</code></td><td>{{ task.description }}</td></tr>
<tr><td><code>finished</code></td><td>{{ task_origin_defectquote.finished|timezone:task_origin_defectquote.timezone|date:'H:i'|default:"(still in progress)" }}</td></tr>
<tr><td><code>get_duration</code></td><td>{{ task_origin_defectquote.get_duration|duration }}</td></tr>
<tr><td><code>get_type_display</code></td><td>{{ task_origin_defectquote.get_type_display }}</td></tr>
<tr><td><code>get_uuid_approval_url</code></td><td>{{ task_origin_defectquote.get_uuid_approval_url|absolute }}</td></tr>
<tr><td><code>ref</code></td><td>{{ task.ref }}</td></tr>
<tr><td><code>started</code></td><td>{{ task_origin_defectquote.started|timezone:task_origin_defectquote.timezone|date:'d/m/Y H:i' }}</td></tr>
<tr><td><code>technician</code></td><td>{{ task_origin_defectquote.technician }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

{% if task_origin_defectquote.ref %}
<div class="...">
<a href="{{ task_origin_defectquote.get_uuid_approval_url|absolute }}">
{{ task_origin_defectquote.ref }}
{% include "reports/library/arrow-up-right-from-square-icon.svg" with width="..." height="..." %}

```

</details>


---

```django

<td>{{ tasksession.get_type_display }}</td>
<td>{{ tasksession.technician }}</td>
<td>{{ tasksession.started|timezone:tasksession.timezone|date:'d/m/Y H:i' }} -
{{ tasksession.finished|timezone:tasksession.timezone|date:'H:i'|default:"(still in progress)" }}</td>
<td>{{ tasksession.get_duration|duration }}</td>

```

</details>


</body>
</html>## technician

<details class="expandable-section">
<summary>Found in files</summary>

- [AARHUSFIRE] - [templates] - [Service Report (Prompts)](https://AARHUSFIRE.onuptick.com/configuration/templates)
- [ABACUSFAS] - [emails] - [test](https://ABACUSFAS.onuptick.com/configuration/emails)

</details>

### Properties

<table>
<tr><th>Property</th><th>Example Usage</th></tr>
<tr><td><code>accreditations</code></td><td>{% for accreditation in technician.accreditations %}</td></tr>
<tr><td><code>inspected_date</code></td><td>{{ technician.inspected_date }}</td></tr>
<tr><td><code>name</code></td><td>{{accreditation.name}}</td></tr>
<tr><td><code>number</code></td><td>{{ accreditation.number }}</td></tr>
</table>

<details class="expandable-section">
<summary>Usage Examples</summary>

```django

<td>{{ technician.inspected_date }}</td>
<td>
{% for accreditation in technician.accreditations %}
<div>{{accreditation.name}}: {{ accreditation.number }}</div>
{% endfor %}

```

</details>


</body>
</html>

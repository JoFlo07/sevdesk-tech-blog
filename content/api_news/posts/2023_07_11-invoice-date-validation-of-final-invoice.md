---
title: "Invoice date validation of final invoices"
date: 2023-07-11T09:34:22+02:00
description: "API changes"
featured_image: '/img/papierloses-buero.jpg'
---

<b>Status Quo:</b>
<br>
The invoice date of a final invoice can be earlier than the date of an associated partial invoice.
<br><br>
<b>Future:</b>
<br>
The invoice date of a final invoice must be on the same day or later than the highest date of the associated partial invoices.<br><br>
<b>Affected endpoints:</b>
<ul>
<li>
<a href="https://api.sevdesk.de/#tag/Invoice/operation/createInvoiceByFactory">POST /api/v1/Voucher/Factory/saveInvoice/</a> 
</li>
</ul>

If you want to create invoices from orders you should use <br><a href="https://api.sevdesk.de/#tag/Invoice/operation/createInvoiceFromOrder">POST /api/v1/Invoice/Factory/createInvoiceFromOrder</a>

<b>Release:</b> 05.09.2023 (4.162)
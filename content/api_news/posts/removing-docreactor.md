---
title: "Removing public access of the Doc Server"
description: "API changes"
featured_image: '/img/gwg_abschreibung_hero.jpg'
---


The Doc Server (docreactor.sevdesk.de), which can be used to generate PDFs for invoices among other things, will no longer be directly accessible.

Status Quo:<br>
PDF files can be generated using the Doc Server via docreactor.sevdesk.de.

Future:<br>
The Doc Server (docreactor.sevdesk.de) will no longer be accessible.
Instead, PDFs can be generated using the documented API endpoints.

For example, see the endpoints below:

<ul>
<li><a href="https://api.sevdesk.de/#tag/Invoice/operation/invoiceGetPdf">https://api.sevdesk.de/#tag/Invoice/operation/invoiceGetPdf</a></li>
<li><a href="https://api.sevdesk.de/#tag/Layout/operation/updateInvoiceTemplate">https://api.sevdesk.de/#tag/Layout/operation/updateInvoiceTemplate</a></li>
</ul>
<b>Release:</b> 24.07.2023 (4.159)
---
title: "Upcoming changes 24.07.2023"
date: 2023-06-13T11:58:42+01:00
description: "API changes"
featured_image: '/img/papierloses-buero.jpg'
---


The creation of documents without positions will no longer be allowed in the future. This concerns the creation of these new documents:
<li>Offers - Estimate / Proposal <code>order_type = 'AN'</code></li>
<li> Orders - Order confirmation <code>order_type = 'AB'</code></li>
<li> Delivery notes <code>order_type = 'LI'</code></li>
<li>Credit notes</li>
<br>
This is mandatory to create a correct accounting entry and to guarantee clean data in the export. The following endpoints are affected:
<br><br>
<li> <code>/api/v1/CreditNote/Factory/saveCreditNote</code>
    <ul class="custom-list"><li>creditNotePosSave must contain at least one item when creating new credit notes.</li></ul>
</li>
<li><code>/api/v1/Order/Factory/saveOrder</code>
    <ul class="custom-list"><li>orderPosSave must contain at least one item when creating new offers, orders, delivery notes.</li></ul>
</li>
<li><code>/api/v1/CreditNote/Factory/createFromInvoice</code>
    <ul class="custom-list">
        <li>the associated invoice must have at least one item</li>
        <li>the endpoint is new and has only been documented since 22.05.2023 (so probably irrelevant)</li>
    </ul>
</li>
<li><code>/api/v1/CreditNote/Factory/createFromVoucher</code>
    <ul class="custom-list">
        <li>the associated voucher must have at least one item</li>
        <li>the endpoint is new and has only been documented since 22.05.2023 (i.e. probably irrelevant).</li>
    </ul>
</li>

Status Quo:
Offers, orders, delivery notes and credit notes can be created without a position.

Future:
Offers, orders, delivery notes and credit notes must have at least one position when created.
Already created offers, orders, delivery notes or credit notes without positions are not affected.

<b>Release:</b> 24.07.2023 (4.159)
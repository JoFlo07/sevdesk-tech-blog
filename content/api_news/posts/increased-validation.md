---
title: "Increased voucher validation"
date: 2023-06-19T11:51:42+01:00
description: "API changes"
featured_image: '/img/ratgeber_hero_guvkonto-abschliessen.jpg'
---

Vouchers will be validated more strongly in the future.
The endpoint affected is <a href="https://api.sevdesk.de/#tag/Voucher/operation/createVoucherByFactory">/api/v1/Voucher/Factory/saveVoucher/</a>
 
Validation can be tested during a transition period using the HTTP header <code>X-Version: 1.1</code>.<br><br>
<b>Status Quo:</b><br>
Many inputs are accepted via the API that are not correct from an accounting point of view. Invalid values are accepted and mandatory information that is required for correct accounting is missing.<br><br>
<b>Future:</b><br>
Validation and error message in case of invalid input based on API documentation.<br><br>
<b>Release:</b> 27.06.2023 (4.157)
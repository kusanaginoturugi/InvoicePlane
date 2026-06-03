# Japanese Localization Notes

## Plan

- Add the `japanese` language pack used by the CodeIgniter 3 application.
- Add Japanese PDF invoice and quote templates without changing the default English templates.
- Keep zero-decimal yen display local to the Japanese PDF templates.
- Register the Japanese templates in the built-in template allowlist.

## Work Record

- Added `application/language/japanese/` and matched `ip_lang.php`, `gateway_lang.php`, and `custom_lang.php` keys against `application/language/english/`.
- Added `InvoicePlaneJapanese` PDF templates for invoices and quotes.
- Added `InvoicePlaneJapanese` to `Mdl_Templates` for invoice and quote PDF template selection.
- Added `uploads/inkan.png`, a generic transparent PNG seal image used by the Japanese invoice PDF template.
- Updated `.gitignore` files so the Japanese language files, templates, and seal asset are tracked.

## Handoff

- In Settings, choose `Japanese` for language.
- In Settings, choose `InvoicePlaneJapanese` for the PDF invoice template.
- In Settings, choose `InvoicePlaneJapanese` for the PDF quote template.
- The Japanese PDF templates remove trailing `.00` or `,00` from currency display only in those templates.
- The seal image is loaded from `uploads/inkan.png`.

## Verification

- `php -l` passed for Japanese language files.
- `php -l` passed for both Japanese PDF templates.
- `php -l` passed for `application/modules/invoices/models/Mdl_templates.php`.
- Japanese language keys match the English `ip_lang.php`, `gateway_lang.php`, and `custom_lang.php` keys.

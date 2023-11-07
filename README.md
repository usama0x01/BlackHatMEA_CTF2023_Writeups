
Solutions for BlackHat MEA challenges

## Warm me up

Visiting home page displays a link to login page.

![1](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/0f912fac-3663-4717-a1da-94196f398948)

Also, upon visiting homepage, a Cookie named `session` is returned in headers. Base64 decoding first part before dot (.) shows an OTP. This OTP was later tried in OTP field.

![2](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/7529a164-59e7-401e-a5a0-454f5162548a)

Visiting Login page displays a form to enter Username, Password and OTP.

![3](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/8aa8c8b9-617b-4c5c-b4e7-4d5dba63f05c)

Using single quote in `username` parameters gives error while using double quotes gives no error.

![4](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/e4a4670d-0ecf-4103-9080-0c4117d2ede5)

![5](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/6e121136-fa43-4f67-bce2-06d79091844b)

Using `' or 1=1-- -` or `admin'-- -` doesnot login.  

Using `' order by 2-- -` gives no error while `' order by 3-- -` gives error indicating that backend SQL query i using 2 rows.  

Using username as `' UNION SELECT 'admin','admin'-- -` with any password with OTP got from session cookie successfully logs us in and provides new session cookie.

![6](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/af63da6f-57f6-4ceb-b44b-0bb3777ac03d)

Using received session cookie shows up the flag.

![7](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/648b2a85-67ef-4e88-b959-e1d35ec888dc)




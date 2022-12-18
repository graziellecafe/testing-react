# Testing React with Jest and React Testing Library
*Code without tests is bad code - Michael Feathers*

This repository was created to learn about test in React using Jest and React Testing Library. 

## Introduction
In particular, tests are divided into three groups. 

- **Unit tests**  automatically check small parts of a piece of code, usually just one class. They form the base of the pyramid, i.e. most tests are in this category. Unit tests are simple, easier to implement and run quickly. 

**Integration tests** or **service tests**, which check a complete functionality or transaction of a system. So these are tests that use several classes, from different packages, and may also test external components, such as databases. Integration tests require more effort to implement and run more slowly. 

**System tests**, also called **user interface tests** simulate, as faithfully as possible, a system usage session by a real user. Since they are end-to-end tests, they are more expensive, slower, and less numerous. Interface tests are also usually fragile, that is, minimal changes to the interface components may require modifications to these tests.


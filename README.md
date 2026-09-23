# ProbaAleatoire

A small NetBeans/Ant Java exercise that prints examples from four integer random-number generators and demonstrates byte generation with `SecureRandom`.

## Examples

- [`DefautRandom`](src/probaaleatoire/DefautRandom.java) uses Java's `java.util.Random`.
- [`XORShift`](src/probaaleatoire/XORShift.java) is a custom xorshift example seeded from `System.nanoTime()`.
- [`RecetteNumerique`](src/probaaleatoire/RecetteNumerique.java) combines linear-congruential, xorshift and multiply-with-carry steps.
- [`SecureRandomJava`](src/probaaleatoire/SecureRandomJava.java) uses `java.security.SecureRandom` to generate an integer.

The configured entry point, [`ProbaAleatoire`](src/probaaleatoire/ProbaAleatoire.java), prints one integer from each example. It then calls [`GenererCleCrypto`](src/probaaleatoire/GenererCleCrypto.java) to print hexadecimal byte samples at several sizes, from 128 to 4096 bits.

These are illustrative examples, not a statistical test suite or benchmark. The custom generators are not suitable for cryptographic use. Although the byte-sample example uses `SecureRandom`, it prints the values to standard output and does not implement key storage or lifecycle management. Do not use this project for production key management.

## Running

Open the repository as an existing NetBeans Ant project and run `probaaleatoire.ProbaAleatoire`. The project metadata targets Java source and bytecode level 1.7, and `GenererCleCrypto` uses `javax.xml.bind.DatatypeConverter`; select a compatible JDK. No automated test sources are included.

See the [licence](LICENSE).

# Glossary

A glossary of widely used terms, we assume knowledge of widely-used
cryptographic nomenclature.

-   __Token__: A sequence of bytes generated by the client
-   __Hash-to-curve__: The method by which a sequence of bytes are encoded as a point on a specific elliptic curve. Sometimes referred to as "h2c" for short.
-   __Blinded token__: The elliptic curve point `P = rT`, where `T = h2c(token)` and `r` is some randomly specified scalar value.
-   __Secret key__: A scalar value `k` generated by the server.
-   __Commitments__: A pair of trusted curve points `(G,H)` issued by the server where `H = kG`.
-   __Signed token__: An elliptic curve point `Q = kP`, where `k` is the secret key of the server.
-   __DLEQ proof__: A discrete log equivalence proof over `(G,H,P,Q)` that allows proving (in non-interactive zero-knowledge, aka NIZK) that `log_P(Q) == log_G(H)`.
-   __Token issuance__: A protocol between a client and a server that allows a client to receive signed, blinded tokens from the server. The protocol ensures that the server response always uses the same secret key `k`, until key rotation occurs.
-   __Token redemption__: A protocol between a client and a server that allows a client to prove to the server that they have a signed token under the server's secret key. They achieve this without revealing the original step in which the client received the signed token.

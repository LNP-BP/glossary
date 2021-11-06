# LNP/BP Glossary

Meaning of terms used accross LNP/BP protocols, including bitcoin, lightning, RGB etc (i.e. even those defined in BIPs and BOLTs, not only LNPBP standards)

## Bitcoin protocol

### Taproot-specific terminology

*Internal key*: x-only key for which a secret key is known; may be a result of multiple key aggregation.

*Output key*: x-only key used as serialized 32-byte v1 witness program. Produced from tap-tweaked internal key, where tap tweak is either tagged self-hash-tweak - or tweak with tagged script merkle root for key-path based spends.

*Control block*: data structure from the last witness stack element (after removal of optional annex) if there more than one element is present. Structure consists of 7 bits of leaf version, one bit of parity flag and a merkle path for the script key spend.

*Hoffman tree*:

*Tapscript*:

*Parity flag*: specifies parity flag of the output key. Used for batch signature verification. Encoded as least significant bit in the first byte of the last witness stack element after removal of the optional *annex*.

*Leaf version*: specifies script version used in specific merkle path. Allows use of different types of script in different branches. Shared accross different witness version >=1. Can be only even with a fixed set of allowed values. Current Tapscript (BIP-342) uses leaf version `0xC0`. Encoded as 7 most significant bits in the first byte of the last witness stack element after removal of the optional *annex*.

*Annex*:

*Ext code*:

*Sighash prefix*:

*Tapleaf hash*:

*Key version*:

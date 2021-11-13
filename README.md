# LNP/BP Glossary

Meaning of terms used accross LNP/BP protocols, including bitcoin, lightning, RGB etc (i.e. even those defined in BIPs and BOLTs, not only LNPBP standards)

## Bitcoin protocol

### Taproot-specific terminology

**Internal key**: x-only key for which a secret key is known; may be a result of multiple key aggregation.

**Output key**: x-only key used as serialized 32-byte v1 witness program. Produced from tap-tweaked internal key, where tap tweak is either tagged self-hash-tweak - or tweak with tagged script merkle root for key-path based spends.

**Control block**: data structure from the last witness stack element (after removal of optional annex) if there more than one element is present. Structure consists of 7 bits of leaf version, one bit of parity flag and a merkle path for the script key spend.

**Huffman tree**:

**Tapscript**:

**Parity flag**: specifies parity flag of the output key. Used for batch signature verification. Encoded as least significant bit in the first byte of the last witness stack element after removal of the optional *annex*.

**Leaf version**: specifies script version used in specific merkle path. Allows use of different types of script in different branches. Shared accross different witness version >=1. Can be only even with a fixed set of allowed values. Current Tapscript (BIP-342) uses leaf version `0xC0`. Encoded as 7 most significant bits in the first byte of the last witness stack element after removal of the optional *annex*.

**Annex**:

**Sighash prefix**:

**Sighash epoch**: a way for introducing breaking changes into common signature function (like chaning the order of data serialization in signed message). Should not be used for incremental changes (like adding more data to the signed message), where *ext code* should be used instead.

**Ext code**:

**Tapleaf hash**:

**Key version**: version of public key serialization algorithm for bitcoin script in taproot represented by a single byte. Tapscript uses `0x00`, which indicated x-coord-only key serialization as it is defined in BIP-340. Signature algorithm commits to the key version value (this is the only place where this value is used explicitly). The key serialization is defined at the level of soft-fork and may be changed with (a) change in the length of v1 witness program and (b) new witness version.

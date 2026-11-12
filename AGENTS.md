# Documentation rules

- This repository is the user guide for the LACCP (Local Area Common Clock Protocol).
- Treat ../LACCP as the authoritative source for RTL interfaces and implementation details.
- LACCP is an upper-layer protocol of the MIKUMARI link protocol.
- Treat ../mikumari as the authoritative source for RTL interfaces and implementation details for the MIKUMARI link protocol.
- User guide of the MIKUMARI link is https://ryotarohonda.github.io/ug-mikumari/
- Do not invent or infer protocol specifications that are not supported by source code or release notes.
- Keep technical terminology consistent with the RTL source.
- Write documentation in concise technical English.
- Prefer tables over copied VHDL entity declarations for public interfaces.
- Do not modify unrelated sections.
- Before finishing, compare the documentation changes against the current LACCP source.

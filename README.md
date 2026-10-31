![Banner](banner.png)

# dm-data-pattern-scrambler
Replaces identifiable patterns (e.g., phone number formats, credit card patterns) with random but valid patterns of the same type.  Useful for masking data that adheres to known formats, ensuring compliance while rendering the data unusable. - Focused on Tools designed to generate or mask sensitive data with realistic-looking but meaningless values

## Install
`git clone https://github.com/ShadowGuardAI/dm-data-pattern-scrambler`

## Usage
`./dm-data-pattern-scrambler [params]`

## Parameters
- `-h`: Show help message and exit
- `-p`: No description provided
- `-l`: No description provided
- `-f`: Path to a file to scramble. Overrides input_text argument if present.
- `-o`: Path to the output file. If not provided, prints to stdout.

## Credit card patterns and output path

Credit card numbers are scrambled in these forms: contiguous runs of 13 to 19 digits, dashed groups of four, and spaced groups of four. Digit boundary guards keep a run longer than 19 digits from being partly scrambled: such a run is left unmatched as a whole rather than masking a prefix and leaving the rest in the output.

The output file must not be the input file. If the resolved output path equals the resolved input path, the run refuses at exit 1 before any write, including when the same file is named through a ./ alias or a symlink.

## License
Copyright (c) ShadowGuardAI

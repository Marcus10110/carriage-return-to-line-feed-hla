# Carriage Return to Line Feed Converter

This is a [High Level Analyzer](https://support.saleae.com/extensions/high-level-analyzer-extensions) (HLA) extension for the [Saleae](https://www.saleae.com/) Logic 2 software.

The terminal in the Logic 2 software displays serial analyzer results directly, interpreting standard control characters such as \r, \n, and \t.

Some common serial protocols will use the \r ascii character without a following \n character. The terminal interprets this literally, returning the carriage to the start of the line without advancing.

This has the unfortunate side-effect of over-writing existing contents in the terminal output.

If your application allows it, we suggest editing your serial traffic to use new line characters if appropriate.

However, this simple HLA will simply print the input serial LLA to the console, with \r characters replaced with \n.

It does not try to escape other non-displayable ascii characters, like how the standard serial analyzer does. However, that could be easily added.

## Usage

I recommend disabling the terminal output of your serial LLA, so you don't get both analyzers trying to produce terminal data.

1. Add and configure your serial analyzer.
2. Disable the terminal output from the serial analyzer.
3. Install and add the "Carriage Return to Line Feed Converter" HLA.
4. Select your serial LLA as the input analyzer for the HLA.

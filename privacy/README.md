# Privacy

This guidance should not be considered a blueprint for all things privacy when writing code, but rather a starting point. Privacy should be at the top of mind of every developer and architect as they design and implement solutions.

## Logging

When logging in a solution it is easy to pass messages to a logging class or method and not consider the data it contains. Log files are a treasure trove of data and should be approached with caution when deciding what to log. For example, once could accidentally log personal identifiable information (PII) in logs and as such those log files could be subject to various compliance laws. Consider using a redactor function to pass all logging messages through:

```python
import re


# The Redactor class is used to redact information from a string.
# Currently it is very simple, but can be expanded upon as necessary
class Redactor:
    # function to redact all PII.
    # currently it only redacts email, but other function calls can be added to redact
    # more PII as needed.
    def redact_all_pii(self, message):
        message = self._redact_email(message)
        return message

    # redact emails from the message parameter
    def _redact_email(self, message):
        # substitute the email pattern with [email removed]
        # the pattern below requres at least one non space or @ symbol character for
        # the recipient name.
        # Then the @ symbol followed by at least one non space or @ symbol for the
        # domain.
        # Then a . followed by at least one non space or @ symbol for the top-level
        # domain. This will include domains like "domainsample.co.uk" since ".co.uk"
        # follows the pattern of one period followed by at least one non space or @
        # symbol.
        new_message = re.sub(
            r"[^@\s]+@[^@\s]+\.[^@\s]+", "[email removed]", message  # noqa
        )
        return new_message

```

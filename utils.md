# Utility Functions for Validation, Formatting, Persistence, and HTML Reports

import json
from datetime import datetime


def validate_data(data):
    """Validates the input data."""
    if not isinstance(data, dict):
        raise ValueError("Data must be a dictionary.")
    # Additional validation logic can be added here


def format_data(data):
    """Formats the input data."""
    return json.dumps(data, indent=4)


def save_to_file(filename, data):
    """Saves the formatted data to a file."""
    with open(filename, 'w') as file:
        file.write(format_data(data))


def generate_html_report(data):
    """Generates an HTML report from the input data."""
    html_content = f'<html><body><h1>Report</h1><pre>{format_data(data)}</pre></body></html>'
    return html_content


def save_html_report(filename, data):
    """Saves the HTML report to a file."""
    with open(filename, 'w') as file:
        file.write(generate_html_report(data))

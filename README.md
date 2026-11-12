# Schedule Check

A browser-based static website that detects instructor time conflicts across training schedules. No server or account is required.

## Getting started

Open index.html in a browser. Word imports load Mammoth.js from a CDN and require an internet connection to load the parser. CSV imports do not need an additional parser. Publish this folder on any static host to deploy the app.

## Import format

- Word: include a table with Date, Time, Topic and Instructor’s Name headers. Empty date cells inherit the previous date. Rows without instructors are skipped. Group/Batch columns are optional.
- CSV: required headers are date,start,end,instructor. Optional columns are topic, training and group (or batch). Use 24-hour HH:MM times. Bengali column aliases remain supported.
- JSON: provide an events array, or an object containing an events array. Optional group/batch fields identify groups.

Conflicts appear when the same instructor has overlapping sessions on the same date in different imported schedules. Breaks, sessions without instructors and clashes within the same imported file are excluded. Imported data stays in local storage and does not sync across devices or browsers.

The Teacher load view shows each instructor’s total class time in hours and session count as a bar chart, sorted by total time.

Overlap results show both group names. If no group is specified, the schedule filename is used.

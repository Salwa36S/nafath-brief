Version: NAFATH-V2
Track: AI

## Overview

Emergency 5G needs to stay reliable even when congestion or attacks happen. Different IT areas each protect their own part of that setup. Network slicing gives responders a dedicated logical network with priority resources. The mobile app keeps working offline and then syncs safely when the connection returns. Software clients retry failed requests, and idempotent methods make those retries safe. Data teams use a star schema to report daily usage per region. Cybersecurity follows an incident response lifecycle to detect, contain and recover from attacks. AI predicts congestion so capacity gets added before users feel it. Together, these fields keep the service available when responders need it.

## Software

Safe methods only read from the server and leave everything else alone. GET and HEAD are examples. Idempotent methods like PUT or DELETE leave the server in the same state even if the request is repeated many times. POST is not idempotent. This distinction matters most for retries after a timeout. The client can resend idempotent requests without worry, but resending a POST could create duplicate emergency reports.

Resource: RFC 9110 - HTTP Semantics - https://www.rfc-editor.org/rfc/rfc9110

## AI

Overfitting happens when a model learns the training data too well, including random noise, so it performs well on training data but poorly on new data. Cross-validation helps detect it. The data is split into k folds; each fold is used once for testing while the rest train the model, and the results are averaged. A big gap between training and test scores signals overfitting. Because congestion data is time-dependent, test on later periods.

Resource: Overfitting, Model Tuning, and Evaluation of Prediction Performance - https://link.springer.com/chapter/10.1007/978-3-030-89010-0_4

## Mobile

A responder's app should keep working without a connection. It saves data in a local database and reads from it, so the screen never waits for the network. New reports are stored locally and queued. When the connection returns, the app sends the queued changes to the server in order and then downloads updates. If two devices changed the same record, the app needs a clear rule to resolve the conflict.

Resource: Build an offline-first app - https://developer.android.com/topic/architecture/data-layer/offline-first

## Networking

## Cybersecurity

## Data

## Misconception in My Track

## Open Question

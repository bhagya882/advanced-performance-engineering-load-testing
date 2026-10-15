# Advanced Performance Engineering & Intelligent Load Testing Platform

**Stack:** Java 17, Maven, TestNG, Selenium WebDriver, optional Apache JMeter.

## What it demonstrates
- Controlled concurrent HTTP load against a local demo API
- Load scenario metrics: request count, response-time percentiles, throughput and error rate
- HTML, JSON and CSV reports
- Performance dashboard UI smoke check
- Optional JMeter test plan for an authorized target

## Import into Eclipse
1. Extract this ZIP.
2. Eclipse → File → Import → Existing Maven Projects → select the extracted folder.
3. Configure JDK 17 and Maven Update Project.
4. Run `PerformancePlatformTest.java` as TestNG Test or run `mvn test`.

The automated test starts a local demo API and sends a small controlled workload to localhost only. Results are generated under `reports/`. The dashboard is `dashboard/index.html`; it contains illustrative sample values until a run updates the reports.

## Standalone run
Run `com.bhagya.qa.performance.PerformanceRunner` as a Java application. Optional arguments: users, requests-per-user, scenario; defaults are 10, 10, LOAD.

## JMeter
Open `jmeter/PerformanceTestPlan.jmx` in JMeter. Configure host/port and test only systems you own or are explicitly authorized to test. Start low and scale gradually.

This is an educational starter project, not a production-grade distributed load generator. Selenium is used for a dashboard smoke test; Java HttpClient generates the sample API load.

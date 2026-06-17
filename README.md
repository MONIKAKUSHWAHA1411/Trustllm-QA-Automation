Implementation Order
	1.	.gitignore — fix pre-existing pyc files
	2.	api/__init__.py + api/main.py — verify with curl before writing tests
	3.	tests/requirements-test.txt + tests/conftest.py
	4.	API test files (health → models → leaderboard → results → evaluate → feedback)
	5.	tests/api-testing/test-data.json + test-cases.md + Postman collection JSON
	6.	3 JMeter JMX files
	7.	UI page objects (login_page.py first, then others)
	8.	UI test files (test_login.py → test_navigation.py → test_leaderboard.py → test_run_eval.py)
	9.	GitHub Actions workflows

Trustllm.site

trustllm-automation/

api/
├── __init__.py
├── main.py

tests/
├── api-testing/
│   ├── test_health.py
│   ├── test_models.py
│   ├── test_leaderboard.py
│   ├── test_results.py
│   ├── test_evaluate.py
│   └── test_feedback.py
│
├── ui-testing/
│   ├── test_login.py
│   ├── test_navigation.py
│   ├── test_leaderboard.py
│   ├── test_run_eval.py
│   └── test_feedback.py
│
├── pages/
│   ├── base_page.py
│   ├── login_page.py
│   ├── dashboard_page.py
│   ├── leaderboard_page.py
│   └── evaluation_page.py
│
├── test-data.json
├── test-cases.md
├── conftest.py
└── requirements-test.txt

jmeter/
├── health-load.jmx
├── leaderboard-load.jmx
└── evaluate-load.jmx

.github/workflows/
├── api-tests.yml
├── ui-tests.yml
└── performance-tests.yml

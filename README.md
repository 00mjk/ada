<p align="center">
    <img src="https://media.github.ibm.com/user/376942/files/7bb5fe80-231a-11ed-8440-8c14e1e3c289" height="160">
    <h1 align="center">Airflow DAG Analytics</h1>
</p>

[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)
[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://forthebadge.com)
[![forthebadge](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMTIuOTciIGhlaWdodD0iMzUiIHZpZXdCb3g9IjAgMCAyMTIuOTcgMzUiPjxyZWN0IGNsYXNzPSJzdmdfX3JlY3QiIHg9IjAiIHk9IjAiIHdpZHRoPSIxMDYuMzMiIGhlaWdodD0iMzUiIGZpbGw9IiNFQTQ1NjAiLz48cmVjdCBjbGFzcz0ic3ZnX19yZWN0IiB4PSIxMDQuMzMiIHk9IjAiIHdpZHRoPSIxMDguNjQiIGhlaWdodD0iMzUiIGZpbGw9IiNFQzdDODYiLz48cGF0aCBjbGFzcz0ic3ZnX190ZXh0IiBkPSJNMTUuNjkgMjJMMTQuMjIgMjJMMTQuMjIgMTMuNDdMMTYuMTQgMTMuNDdMMTguNjAgMjAuMDFMMjEuMDYgMTMuNDdMMjIuOTcgMTMuNDdMMjIuOTcgMjJMMjEuNDkgMjJMMjEuNDkgMTkuMTlMMjEuNjQgMTUuNDNMMTkuMTIgMjJMMTguMDYgMjJMMTUuNTUgMTUuNDNMMTUuNjkgMTkuMTlMMTUuNjkgMjJaTTI4LjQ5IDIyTDI2Ljk1IDIyTDMwLjE3IDEzLjQ3TDMxLjUwIDEzLjQ3TDM0LjczIDIyTDMzLjE4IDIyTDMyLjQ5IDIwLjAxTDI5LjE4IDIwLjAxTDI4LjQ5IDIyWk0zMC44MyAxNS4yOEwyOS42MCAxOC44MkwzMi4wNyAxOC44MkwzMC44MyAxNS4yOFpNNDEuMTQgMjJMMzguNjkgMjJMMzguNjkgMTMuNDdMNDEuMjEgMTMuNDdRNDIuMzQgMTMuNDcgNDMuMjEgMTMuOTdRNDQuMDkgMTQuNDggNDQuNTcgMTUuNDBRNDUuMDUgMTYuMzMgNDUuMDUgMTcuNTJMNDUuMDUgMTcuNTJMNDUuMDUgMTcuOTVRNDUuMDUgMTkuMTYgNDQuNTcgMjAuMDhRNDQuMDggMjEuMDAgNDMuMTkgMjEuNTBRNDIuMzAgMjIgNDEuMTQgMjJMNDEuMTQgMjJaTTQwLjE3IDE0LjY2TDQwLjE3IDIwLjgyTDQxLjE0IDIwLjgyUTQyLjMwIDIwLjgyIDQyLjkzIDIwLjA5UTQzLjU1IDE5LjM2IDQzLjU2IDE3Ljk5TDQzLjU2IDE3Ljk5TDQzLjU2IDE3LjUyUTQzLjU2IDE2LjEzIDQyLjk2IDE1LjQwUTQyLjM1IDE0LjY2IDQxLjIxIDE0LjY2TDQxLjIxIDE0LjY2TDQwLjE3IDE0LjY2Wk01NS4wOSAyMkw0OS41MSAyMkw0OS41MSAxMy40N0w1NS4wNSAxMy40N0w1NS4wNSAxNC42Nkw1MS4wMCAxNC42Nkw1MS4wMCAxNy4wMkw1NC41MCAxNy4wMkw1NC41MCAxOC4xOUw1MS4wMCAxOC4xOUw1MS4wMCAyMC44Mkw1NS4wOSAyMC44Mkw1NS4wOSAyMlpNNjYuNzUgMjJMNjUuMjYgMjJMNjUuMjYgMTMuNDdMNzAuNjggMTMuNDdMNzAuNjggMTQuNjZMNjYuNzUgMTQuNjZMNjYuNzUgMTcuMjBMNzAuMTggMTcuMjBMNzAuMTggMTguMzhMNjYuNzUgMTguMzhMNjYuNzUgMjJaTTc0LjU3IDE4LjAwTDc0LjU3IDE4LjAwTDc0LjU3IDE3LjUyUTc0LjU3IDE2LjI4IDc1LjAyIDE1LjMyUTc1LjQ2IDE0LjM3IDc2LjI3IDEzLjg2UTc3LjA3IDEzLjM1IDc4LjExIDEzLjM1UTc5LjE2IDEzLjM1IDc5Ljk2IDEzLjg1UTgwLjc3IDE0LjM1IDgxLjIxIDE1LjI5UTgxLjY1IDE2LjIzIDgxLjY1IDE3LjQ4TDgxLjY1IDE3LjQ4TDgxLjY1IDE3Ljk2UTgxLjY1IDE5LjIxIDgxLjIyIDIwLjE2UTgwLjc5IDIxLjEwIDc5Ljk4IDIxLjYxUTc5LjE3IDIyLjEyIDc4LjEzIDIyLjEyTDc4LjEzIDIyLjEyUTc3LjA5IDIyLjEyIDc2LjI4IDIxLjYxUTc1LjQ3IDIxLjEwIDc1LjAyIDIwLjE3UTc0LjU4IDE5LjIzIDc0LjU3IDE4LjAwWk03Ni4wNiAxNy40Nkw3Ni4wNiAxNy45NlE3Ni4wNiAxOS4zNiA3Ni42MCAyMC4xM1E3Ny4xNSAyMC45MCA3OC4xMyAyMC45MEw3OC4xMyAyMC45MFE3OS4xMSAyMC45MCA3OS42NCAyMC4xNVE4MC4xNyAxOS40MCA4MC4xNyAxNy45Nkw4MC4xNyAxNy45Nkw4MC4xNyAxNy41MVE4MC4xNyAxNi4wOSA3OS42MyAxNS4zNFE3OS4xMCAxNC41OCA3OC4xMSAxNC41OEw3OC4xMSAxNC41OFE3Ny4xNSAxNC41OCA3Ni42MSAxNS4zM1E3Ni4wNyAxNi4wOSA3Ni4wNiAxNy40Nkw3Ni4wNiAxNy40NlpNODcuNjAgMjJMODYuMTIgMjJMODYuMTIgMTMuNDdMODkuMTIgMTMuNDdROTAuNTkgMTMuNDcgOTEuNDAgMTQuMTNROTIuMjAgMTQuNzkgOTIuMjAgMTYuMDVMOTIuMjAgMTYuMDVROTIuMjAgMTYuOTAgOTEuNzkgMTcuNDhROTEuMzcgMTguMDYgOTAuNjQgMTguMzdMOTAuNjQgMTguMzdMOTIuNTUgMjEuOTJMOTIuNTUgMjJMOTAuOTYgMjJMODkuMjUgMTguNzFMODcuNjAgMTguNzFMODcuNjAgMjJaTTg3LjYwIDE0LjY2TDg3LjYwIDE3LjUyTDg5LjEyIDE3LjUyUTg5Ljg3IDE3LjUyIDkwLjMwIDE3LjE1UTkwLjcyIDE2Ljc3IDkwLjcyIDE2LjExTDkwLjcyIDE2LjExUTkwLjcyIDE1LjQzIDkwLjMzIDE1LjA1UTg5Ljk0IDE0LjY4IDg5LjE2IDE0LjY2TDg5LjE2IDE0LjY2TDg3LjYwIDE0LjY2WiIgZmlsbD0iI0ZGRkZGRiIvPjxwYXRoIGNsYXNzPSJzdmdfX3RleHQiIGQ9Ik0xMTkuOTQgMjJMMTE3LjUxIDIyTDEyMS4yMiAxMy42MEwxMjMuNTYgMTMuNjBMMTI3LjI4IDIyTDEyNC44MSAyMkwxMjQuMTUgMjAuMzdMMTIwLjYwIDIwLjM3TDExOS45NCAyMlpNMTIyLjM3IDE1LjkzTDEyMS4yOSAxOC42MUwxMjMuNDUgMTguNjFMMTIyLjM3IDE1LjkzWk0xMzMuODEgMjJMMTMxLjQzIDIyTDEzMS40MyAxMy42MEwxMzMuODEgMTMuNjBMMTMzLjgxIDIyWk0xNDEuMzYgMjJMMTM4Ljk4IDIyTDEzOC45OCAxMy42MEwxNDIuODMgMTMuNjBRMTQzLjk3IDEzLjYwIDE0NC44MSAxMy45OFExNDUuNjUgMTQuMzUgMTQ2LjEwIDE1LjA2UTE0Ni41NiAxNS43NiAxNDYuNTYgMTYuNzFMMTQ2LjU2IDE2LjcxUTE0Ni41NiAxNy42MiAxNDYuMTMgMTguMzBRMTQ1LjcxIDE4Ljk4IDE0NC45MSAxOS4zNkwxNDQuOTEgMTkuMzZMMTQ2LjcyIDIyTDE0NC4xOCAyMkwxNDIuNjYgMTkuNzdMMTQxLjM2IDE5Ljc3TDE0MS4zNiAyMlpNMTQxLjM2IDE1LjQ3TDE0MS4zNiAxNy45M0wxNDIuNjggMTcuOTNRMTQzLjQxIDE3LjkzIDE0My43OSAxNy42MVExNDQuMTYgMTcuMjkgMTQ0LjE2IDE2LjcxTDE0NC4xNiAxNi43MVExNDQuMTYgMTYuMTIgMTQzLjc5IDE1Ljc5UTE0My40MSAxNS40NyAxNDIuNjggMTUuNDdMMTQyLjY4IDE1LjQ3TDE0MS4zNiAxNS40N1pNMTUzLjczIDIyTDE1MS4zNSAyMkwxNTEuMzUgMTMuNjBMMTU3Ljk0IDEzLjYwTDE1Ny45NCAxNS40NEwxNTMuNzMgMTUuNDRMMTUzLjczIDE3LjI4TDE1Ny40NCAxNy4yOEwxNTcuNDQgMTkuMTJMMTUzLjczIDE5LjEyTDE1My43MyAyMlpNMTY4LjkyIDIyTDE2Mi41MyAyMkwxNjIuNTMgMTMuNjBMMTY0LjkxIDEzLjYwTDE2NC45MSAyMC4xMUwxNjguOTIgMjAuMTFMMTY4LjkyIDIyWk0xNzIuOTEgMTcuODBMMTcyLjkxIDE3LjgwUTE3Mi45MSAxNi41NSAxNzMuNTEgMTUuNTVRMTc0LjEyIDE0LjU2IDE3NS4xOCAxNC4wMFExNzYuMjQgMTMuNDMgMTc3LjU3IDEzLjQzTDE3Ny41NyAxMy40M1ExNzguOTAgMTMuNDMgMTc5Ljk3IDE0LjAwUTE4MS4wMyAxNC41NiAxODEuNjQgMTUuNTVRMTgyLjI0IDE2LjU1IDE4Mi4yNCAxNy44MEwxODIuMjQgMTcuODBRMTgyLjI0IDE5LjA1IDE4MS42NCAyMC4wNFExODEuMDMgMjEuMDQgMTc5Ljk3IDIxLjYwUTE3OC45MSAyMi4xNyAxNzcuNTcgMjIuMTdMMTc3LjU3IDIyLjE3UTE3Ni4yNCAyMi4xNyAxNzUuMTggMjEuNjBRMTc0LjEyIDIxLjA0IDE3My41MSAyMC4wNFExNzIuOTEgMTkuMDUgMTcyLjkxIDE3LjgwWk0xNzUuMzEgMTcuODBMMTc1LjMxIDE3LjgwUTE3NS4zMSAxOC41MSAxNzUuNjEgMTkuMDVRMTc1LjkxIDE5LjYwIDE3Ni40MyAxOS45MFExNzYuOTQgMjAuMjAgMTc3LjU3IDIwLjIwTDE3Ny41NyAyMC4yMFExNzguMjEgMjAuMjAgMTc4LjczIDE5LjkwUTE3OS4yNCAxOS42MCAxNzkuNTQgMTkuMDVRMTc5Ljg0IDE4LjUxIDE3OS44NCAxNy44MEwxNzkuODQgMTcuODBRMTc5Ljg0IDE3LjA5IDE3OS41NCAxNi41NFExNzkuMjQgMTYgMTc4LjczIDE1LjcwUTE3OC4yMSAxNS40MCAxNzcuNTcgMTUuNDBMMTc3LjU3IDE1LjQwUTE3Ni45NCAxNS40MCAxNzYuNDIgMTUuNzBRMTc1LjkxIDE2IDE3NS42MSAxNi41NFExNzUuMzEgMTcuMDkgMTc1LjMxIDE3LjgwWk0xODkuMDUgMjJMMTg2LjMzIDEzLjYwTDE4OC43OCAxMy42MEwxOTAuNDcgMTguOTZMMTkyLjI0IDEzLjYwTDE5NC40MyAxMy42MEwxOTYuMTIgMTkuMDFMMTk3Ljg4IDEzLjYwTDIwMC4xNSAxMy42MEwxOTcuNDMgMjJMMTk0Ljg4IDIyTDE5My4yOCAxNi44OUwxOTEuNjAgMjJMMTg5LjA1IDIyWiIgZmlsbD0iI0ZGRkZGRiIgeD0iMTE3LjMzIi8+PC9zdmc+)](https://forthebadge.com)


<br>

<h2><img height="20" src="https://media.github.ibm.com/user/376942/files/ebc48480-231a-11ed-8b70-30e2b8893504">&nbsp;&nbsp;What is ADA?</h2>

ADA is a microservice with the main purpose to retrieve key analytics metrics for task and dag level from your Airflow database instance.


<h2>Contents</h2>

- [Business context](#business-context)
- [Deployment](#deployment)
	- [Code Engine tutorial](#code-engine-tutorial)
- [Engine compatibility](#engine-compatibility)

<h2>Business context</h2>

The amount of stuck pods became an increasing pain for us: whenever they happened, they would demand support requests followed by analysis that often resulted in simple and manual actions. Based on that, there arose a need to automate this process, in other words, to make us able to identify a stuck pod and take the appropriate action in a fully automatic way, transparent for both developer and user.

Well, but what is the best way to identify a stuck pod? The answer is simple: based on historical data, we can tell if something is taking longer than it should to run. That’s when the perfect opportunity arose to implement, for the first time, a **Serverless computing module**.

<h2>Deployment</h2>

<h3>Code Engine tutorial</h3>

For more information, access https://cloud.ibm.com/docs/codeengine.

<h2>Engine compatibility</h2>
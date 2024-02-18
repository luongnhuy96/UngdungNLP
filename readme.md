# using alphacodium for trading strategy and backtest

## Architecture
<img src="https://github.com/luongnhuy96/UngdungNLP/blob/main/images/proposed_flow.png">



## Installation
(0) clone AlphaCodium Github:`git clone https://github.com/Codium-ai/AlphaCodium.git`
(1) setup a virtual environment and run: `pip install -r requirements.txt`

(2) Duplicate the file `alpha_codium/settings/.secrets_template.toml`, rename it as `.secrets.toml`, and fill in your OpenAI API key:
```
[openai]
key = "..."
```

### Solving a new problem (CodeContest format)
To solve a custom problem with AlphaCodium, first create a json file that includes the CodeContest problem fields, and then from the root folder run:
```
python -m alpha_codium.solve_my_problem \
--my_problem_json_file /path/to/my_problem.json
```
- The `my_problem_json_file` is the path to to the custom problem json file.

See the `my_problem_example.json` to see an example of a custom problem. The json file should include the following fields:
- `name` is the name of the problem.
- `description` is a description of the problem.
- (optional) `public_tests` with the following fields:
  - `input` is a list of strings that represent the input.
  - `output` is a list of strings that represent the output.
- (optional) `private_tests`, that follows the same structure as `public_tests`
- (optional) `generated_tests`, that follows the same structure as `public_tests`

## How to run
```bash

python -m alpha_codium.solve_my_problem --my_problem_json_file D:/UngdungNLP/AlphaCodium/my_problem_example_Y_stock.json >
 output_tradingstrategy.txt

python -m alpha_codium.solve_my_problem --my_problem_json_file D:/UngdungNLP/AlphaCodium/my_problem_example_Y_backtestv3.json > output_backtest.txt
```
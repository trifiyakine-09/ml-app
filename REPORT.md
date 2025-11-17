# DevOps Assignment Report

## Task 1: Prepare the ML Project
- Instead of forking the repo, I downloaded the ZIP of the source repo,added to it the Dockerfile file and created my own repository `ml-app` on GitHub.
- The project structure includes:
  - src/: Python scripts (train.py, predict.py, model.py, utils.py, data_loader.py)
  - requirements.txt: dependencies for the project
  - Dockerfile: added to containerize the app
  - tests
## Task 2: Run the ML Scripts
1. Activated virtual environment
   - Windows: `.\.venv\Scripts\Activate.ps1`
2. Installed dependencies: `pip install -r requirements.txt`
   ![Run Screenshot](Screenshots/Run.png)
3. Trained the model:
   - Command: `python src/train.py`
   - Output: model trained, accuracy 0.9667, example prediction: [6.7, 3.0, 5.2, 2.3] → virginica
   ![train](Screenshots/train.png)
4. Made predictions:
   - Command: `python src/predict.py`
   - Output: example predictions printed
    ![predit](Screenshots/predict.png)
## Task 3: Unit Tests

- The `tests/test_model.py` file contains meaningful pytest tests for core ML functionality:
  1. Model initialization
  2. Model training
  3. Model prediction
  4. Model evaluation
  5. Save/load model
  6. Data loading
- Ran locally using: `python -m pytest tests/ --rootdir=.`
- Output: all 6 tests passed (see screenshot)
- Note: There were some warnings from sklearn regarding L-BFGS-B solver, which do not affect test results.
    ![test](Screenshots/tests.png)
## Task 4: Linting & Formatting

To ensure code quality and maintainability, we added **flake8** as a linter for the project.

- Configuration
A minimal `.flake8` configuration file was created:
    ![flake](Screenshots/flakeFile.png)
    **max-line-length**: Allows lines up to 120 characters.
    **exclude**: Ignores virtual environment, cache files, and test folder.
- Running Flake8
To run the linter, use:
    ![flakeRun.png](Screenshots/flakeRun.png)
- The screenshot below shows the `flake8` linting results after fixing issues:
    ![flakeResults.png](Screenshots/flakeResults.png)
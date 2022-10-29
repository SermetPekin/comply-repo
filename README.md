[![Python package](https://github.com/SermetPekin/comply-repo/actions/workflows/python-package.yml/badge.svg)](https://github.com/SermetPekin/comply-repo/actions/workflows/python-package.yml) [![PyPI](https://img.shields.io/pypi/v/comply)](https://img.shields.io/pypi/v/comply) [![Supported Python Versions](https://img.shields.io/pypi/pyversions/comply)](https://pypi.org/project/comply/) [![Downloads](https://pepy.tech/badge/comply/week)](https://pepy.tech/project/comply)

# comply

    from comply import check

### checks if user's python version is compatible with your project

    def check(
            min_version: str,
            max_version: str,
            min_msg: t.Union[str, t.Callable] = default_min_msg,
            max_msg: t.Union[str, t.Callable] = default_max_msg,
            complyible_msg: t.Union[str, t.Callable] = default_comply_msg,
            verbose: bool = True,
            mock_sys_version: t.Union[str, bool] = False, # for test purposes
    
    ):


###  Use case 1 : main file on your project to continue or stop running 
>  you may use it on the main file of your project 
> and create a conditional and decide what to do next 

    if check(
            min_version="3.7",
            max_version="3.11",
            min_msg="Your version is less than minimum.",
            verbose=True,

        ) is False : 
            sys.exit(0) # return # or just exit
    # if user's python has a version of lets say 3.4 this will print your customized message and exit.


> just warn the user and continue

    if check(
            min_version="3.7",
            max_version="3.10",
            min_msg="Your version is less than minimum.",
            max_msg="Your version is greater than the minimum.",
            verbose=True,

        ) is False : 
            pass   
    # if user's machine has a python with version of 
    # lets say 3.4 this will print your customized message and continue .


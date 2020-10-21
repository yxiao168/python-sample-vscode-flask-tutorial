# Python/Flask Tutorial for Visual Studio Code

https://github.com/yxiao168/python-sample-vscode-flask-tutorial



* This sample contains the completed program from the tutorial, make sure to visit the link: [Using Flask in Visual Studio Code](https://code.visualstudio.com/docs/python/tutorial-flask). Intermediate steps are not included.
* It also contains the Dockerfile and uwsgi.ini files necessary to build a container with a production server. The resulting image works both locally and when deployed to Azure App Service. See [Deploy Python using Docker containers](https://code.visualstudio.com/docs/python/tutorial-deploy-containers).

## Navigation

The `startup.py` file, for its part, is specifically for deploying to Azure App Service on Linux without containers. Because the app code is in its own *module* in the `hello_app` folder (which has an `__init__.py`), trying to start the Gunicorn server within App Service on Linux produces an "Attempted relative import in non-package" error. The `startup.py` file, therefore, is just a shim to import the app object from the `hello_app` module, which then allows you to use startup:app in the Gunicorn command line (see `startup.txt`).

## Running
After selecting the python inteprator, run the content in the **`startup.txt`**
```
$ . ./startup.txt 
[2020-10-21 14:26:48 -0400] [24998] [INFO] Starting gunicorn 20.0.4
[2020-10-21 14:26:48 -0400] [24998] [INFO] Listening at: http://0.0.0.0:8000 (24998)
[2020-10-21 14:26:48 -0400] [24998] [INFO] Using worker: sync
[2020-10-21 14:26:48 -0400] [25000] [INFO] Booting worker with pid: 25000
[2020-10-21 14:26:49 -0400] [25008] [INFO] Booting worker with pid: 25008
[2020-10-21 14:26:49 -0400] [25009] [INFO] Booting worker with pid: 25009
[2020-10-21 14:26:49 -0400] [25010] [INFO] Booting worker with pid: 25010
[2020-10-21 14:32:52 -0400] [24998] [INFO] Handling signal: winch
[2020-10-21 14:32:52 -0400] [24998] [INFO] Handling signal: winch
[2020-10-21 14:35:06 -0400] [24998] [INFO] Handling signal: winch
[2020-10-21 14:35:13 -0400] [24998] [INFO] Handling signal: winch
```

## Contributing

Contributions to the sample are welcome. When submitting changes, also consider submitting matching changes to the tutorial, the source file for which is [tutorial-flask.md](https://github.com/Microsoft/vscode-docs/blob/master/docs/python/tutorial-flask.md).

Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot automatically determines whether you need to provide a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions provided by the bot. You will only need to do this once across all repos using our CLA.

## Additional details

* This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
* For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
* Contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

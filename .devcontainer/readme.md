# Steps for Docker on Terminal:
1. If image is not built , build it by running(make sure dockerfile is named dockerfile):
    ```
    cd .devcontainer
    docker build -t test_repo .
    ```      
2. Run from directory to mount: 
   ```
    docker run --name test_repo_container -it --rm -v ${PWD}/:/workspace -w /workspace test_repo
   ``` 
3. If container doesn't open and terminal says "container started", in another terminal run: ``` docker ps -a``` to get container id then: ``` docker exec -it \<containerID\> ```


# Steps for Docker with Dev Containers(easier alternative to the above):
1. Install dev containers extension in vscode.
2. Make sure that vscode is opened with parent repo of .devcontainer repo(you can include code to mount in container as sibling repos to .devcontainer repo)
3. ctrl + shift + p to open command palette
4. Find and click on **Dev Containers: Rebuild and Reopen in Container**
5. If you would like to use docker for another folder, copy the .devcontainer folder into that folder; then repeat steps 1 to 4. 


## Notes:
1. If you are running on windows computer, use vim run :set ff=unix then :wq 

# 🌀 T.O.R.A — Transforming Object Reconstructing Application

> Prototype Assignment: Convert a Photo or Text into a Simple 3D Model (.obj)

---

## ✨ About This Project

**T.O.R.A** (Transforming Object Reconstructing Application) is a prototype application developed as an assignment. Its core function is to take a **single image** of an object (such as a toy, chair, or car) and reconstruct a **partial 3D model** from it using AI techniques.

The application provides a simple **drag-and-drop GUI** built with Gradio. Upon processing the image, it outputs:

* A **depth map** visualizing the perceived distance of points in the image.
* A **mesh preview** showing the generated 3D structure.
* A downloadable **`.obj` file** of the reconstructed 3D model.

---

## 🎯 Why "Partial" 3D?

This prototype currently processes **only one image** of the object. Since there is no information about the back or hidden sides of the object from a single viewpoint, the generated mesh only covers the **visible surface** captured in the input image. Therefore, the output is a **partial 3D reconstruction**, not a complete 3D model.

---

## ⚙️ Environment Setup (Important)

> ✅ Tested with **Python 3.8**
> ⚠️ **Not compatible with latest Python versions** (e.g., 3.11+) due to specific version requirements of libraries like `open3d`. You **must** use Python 3.8 or a compatible older Python 3 version.
> ❌ Do **not** use Python 3.11+ — may crash or raise import errors

### Step-by-Step Setup:

1.  **Install Python 3.8 (if not already installed):**
    * If you don't have Python 3.8, download and install the appropriate version for your operating system from the official Python website: [https://www.python.org/downloads/release/python-380/](https://www.python.org/downloads/release/python-380/)
    * **Important:** During installation on Windows, it's highly recommended to check the box that says "Add Python 3.8 to PATH".

2.  **Open your Terminal or Command Prompt:**
    * Navigate to the directory where you have cloned or downloaded the project files (this directory should contain the project's `.ipynb` notebook file and any other necessary scripts/assets).

3.  **Create a Virtual Environment:**
    * Run the following command. This creates a dedicated, isolated Python environment named `venv` within your project directory, using your installed Python 3.8 interpreter.
        ```bash
        python3.8 -m venv venv
        ```
    * *Explanation:* `python3.8` explicitly uses your installed Python 3.8 interpreter. `-m venv` invokes the standard module for creating virtual environments. `venv` is the name of the directory that will be created for the environment.

4.  **Activate the Virtual Environment:**
    * Before installing packages or running code, you must activate the environment. This ensures that any libraries you install are placed inside this `venv` and that you use the Python interpreter within this environment.
    * **On macOS/Linux:**
        ```bash
        source venv/bin/activate
        ```
    * **On Windows:**
        ```cmd
        venv\Scripts\activate
        ```
    * *Verification:* After successful activation, your terminal prompt will usually change to include the name of the environment, for example, `(venv) your_user@your_computer:~/tora_project $`.

5.  **Install Dependencies:**
    * With the virtual environment active, install all required libraries using `pip`. Run this single command:
        ```bash
        pip install torch transformers numpy Pillow open3d==0.18.0 trimesh pyvista gradio notebook
        ```
    * *Included:* This command installs the core AI libraries (`torch`, `transformers`), data handling (`numpy`, `Pillow`), 3D processing (`open3d`, `trimesh`, `pyvista`), the GUI framework (`gradio`), and `notebook` for running the Jupyter Notebook *within this environment*.
    * *Wait:* This step will download and install several potentially large packages. It may take several minutes depending on your internet speed and system performance.

6.  **Start Jupyter Notebook:**
    * Once the dependencies are installed, ensure your virtual environment is still active and you are in the project directory in your terminal. Run:
        ```bash
        jupyter notebook
        ```
    * *What happens:* This command starts the Jupyter server. It will print server information, including URLs, in your terminal. In most cases, it will also automatically open a new tab in your default web browser displaying the Jupyter file explorer for your project directory.

7.  **Open the Project Notebook (`.ipynb` file):**
    * In the Jupyter file explorer that opened in your browser, locate and click on the main project notebook file (it will have a `.ipynb` extension, e.g., `tora_prototype.ipynb`). This will open the notebook interface in a new browser tab.

8.  **Run the Notebook Cells Sequentially:**
    * The project's code is structured within the notebook's code cells. You must execute these cells in the order they appear from top to bottom.
    * Click on the first code cell to select it.
    * Run the cell by clicking the "Run" button in the toolbar at the top of the notebook or by pressing `Shift + Enter` on your keyboard.
    * Wait for each cell to complete execution before running the next one. The input prompt changes from `In [*]` (running) to `In [number]` (finished).

9.  **Access the T.O.R.A GUI:**
    * The final code cell in the notebook is responsible for launching the Gradio user interface (likely using a command like `iface.launch()`).
    * After you run this last cell and it finishes executing, look at the output displayed directly below that cell within the notebook interface. Alternatively, check the terminal window where you originally ran the `jupyter notebook` command.
    * You will see output containing URLs similar to this:
        ```
        Running on local URL:  [http://127.0.0.1:7860/](http://127.0.0.1:7860/)
        To create a public link, set `share=True` in `launch()`.
        ```
    * **Ctrl+Click (or Cmd+Click on macOS)** on the `http://127.0.0.1:7860/` (or similar local address) URL displayed in the output. This will open the T.O.R.A application's drag-and-drop GUI in your web browser.

---

## 🚀 How to Use

Once the Gradio GUI is open in your browser:

1.  Simply **drag and drop** a single image of an object into the designated area in the GUI.
2.  Follow any instructions or click a "Process" or "Generate" button if present in the interface.
3.  Wait for the processing to complete.

---

## 💾 Output

After processing, the GUI will display:

* A **Depth Map** visualization.
* A **Mesh Preview** showing the generated partial 3D model.
* A link or button to **download** the reconstructed 3D model as a **`.obj` file**.

---

## 🚧 Limitations

As a prototype using a single image:

* The reconstructed model is **partial**, representing only the visible surface from the camera's perspective.
* Occluded parts of the object are not reconstructed.
* The quality of the reconstruction is highly dependent on the input image quality, lighting, and the object's complexity.

---

## License

This project is a prototype developed for an assignment and is not intended for commercial use or distribution without further development and licensing considerations.

---

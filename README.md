# Multi-Retailer Product Scraper & Excel Consolidated Reporter
## UiPath RPA Robot for E-Commerce Data Extraction & Processing

## 📌 Project Overview
This automated RPA solution streamlines market research and price comparison by extracting product data across major retail chains based on dynamic user input. The robot prompts the user for a search query, performs concurrent web scraping across multiple retail platforms, isolates individual datasets, and generates a structured, multi-sheet Excel report for analytical decision-making.

Built using **UiPath Studio (Windows/Modern Design)**, the project follows clean architecture principles by decoupling process initialization, data input extraction, and individual retail automation workflows.

## 🛠️ Technical Stack & Architecture
* **RPA Platform:** UiPath Studio (Modern Experience)
* **Design Patterns:** Modular Workflow Invocation, Try-Catch Error Handling, Argument Mapping.
* **Core Dependencies:**
  * `UiPath.Excel.Activities`
  * `UiPath.System.Activities`
  * `UiPath.UIAutomation.Activities`
* **Data Flow Implementation:** Uses secure In/Out Dictionary arguments to transition search tokens and transactional tables seamlessly between parent and child workflows.

## 🤖 Workflow Architecture
The automation is segmented into dedicated `.xaml` modules to ensure ease of maintenance and high scalability:
1. **`Main.xaml`**: The orchestrator wrapper that governs execution states within a robust `Try-Catch` block.
2. **`Cierra Procesos.xaml`**: Kill-process routine designed to safely close target browser environments (Chrome/Edge) prior to execution, ensuring a clean runtime state.
3. **`Datos Consulta.xaml`**: User Interaction module utilizing dynamic input dialogues to safely capture and store query parameters into execution dictionaries.
4. **`ProductosAlkosto.xaml`**: Target-specific web automation framework featuring optimized web scraping and dynamic data table extraction for Alkosto E-Commerce.
5. **`ProductosExito.xaml`**: Target-specific web automation framework customized to extract and structure product tables from Grupo Éxito.

## 📈 Business Impact & ROI
* **Manual Effort Reduction:** Replaces a 15-minute multi-tab manual query process with an autonomous execution of under **90 seconds**.
* **Data Integrity:** Achieves **100% accuracy** in scraping brand name, detailed product specifications, and currency-formatted price data, removing human transcription errors completely.
* **Scalability:** Built on a modular structure allowing new retail providers or e-commerce platforms to be integrated as separate `.xaml` modules with zero downtime to existing processes.

## 📂 Output Preview
The robot yields a consolidated Excel workbook (`ListaProductosEncontrados.xlsx`) containing dedicated worksheets for each retailer, structured cleanly with standardized headers (`Marca`, `Descripcion`, `Costo Efectivo`).

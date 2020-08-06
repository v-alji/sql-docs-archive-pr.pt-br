---
title: Importar de uma fonte de dados relacional (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 043201cc-fbef-4ed0-bde8-dc5e3a3e8bea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93bb9ba9ba8d40262e4e90e840dcd15ac6826df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582669"
---
# <a name="import-from-a-relational-data-source-ssas-tabular"></a><span data-ttu-id="d7072-102">Importar de uma fonte de dados relacional (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="d7072-102">Import from a Relational Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="d7072-103">Você pode importar dados de uma variedade de bancos de dados relacionais usando o Assistente de Importação de Tabela.</span><span class="sxs-lookup"><span data-stu-id="d7072-103">You can import data from a variety of relational databases by using the Table Import Wizard.</span></span> <span data-ttu-id="d7072-104">O assistente está disponível em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], no menu **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="d7072-104">The wizard is available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Model** menu.</span></span> <span data-ttu-id="d7072-105">Para conectar uma fonte de dados, você deve ter o provedor apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="d7072-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span> <span data-ttu-id="d7072-106">Para obter mais informações sobre os provedores e as fontes de dados com suporte, consulte [Fontes de dados com suporte &#40;SSAS de Tabela&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d7072-106">For more information about supported data sources and providers, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="d7072-107">O Assistente de Importação de Tabela dá suporte a importação de dados das seguintes fontes de dados:</span><span class="sxs-lookup"><span data-stu-id="d7072-107">The Table Import Wizard supports importing data from the following data sources:</span></span>  
  
 <span data-ttu-id="d7072-108">**Bancos de dados relacionais**</span><span class="sxs-lookup"><span data-stu-id="d7072-108">**Relational Databases**</span></span>  
  
-   <span data-ttu-id="d7072-109">Banco de dados do Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7072-109">Microsoft SQL Server database</span></span>  
  
-   <span data-ttu-id="d7072-110">Microsoft SQL Azure</span><span class="sxs-lookup"><span data-stu-id="d7072-110">Microsoft SQL Azure</span></span>  
  
-   <span data-ttu-id="d7072-111">Bancos de dados do Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="d7072-111">Microsoft Access database</span></span>  
  
-   <span data-ttu-id="d7072-112">Microsoft SQL Server Parallel Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="d7072-112">Microsoft SQL Server Parallel Data Warehouse</span></span>  
  
-   <span data-ttu-id="d7072-113">Oracle</span><span class="sxs-lookup"><span data-stu-id="d7072-113">Oracle</span></span>  
  
-   <span data-ttu-id="d7072-114">Teradata</span><span class="sxs-lookup"><span data-stu-id="d7072-114">Teradata</span></span>  
  
-   <span data-ttu-id="d7072-115">Sybase</span><span class="sxs-lookup"><span data-stu-id="d7072-115">Sybase</span></span>  
  
-   <span data-ttu-id="d7072-116">Informix</span><span class="sxs-lookup"><span data-stu-id="d7072-116">Informix</span></span>  
  
-   <span data-ttu-id="d7072-117">IBM DB2</span><span class="sxs-lookup"><span data-stu-id="d7072-117">IBM DB2</span></span>  
  
-   <span data-ttu-id="d7072-118">OLE DB/ODBC</span><span class="sxs-lookup"><span data-stu-id="d7072-118">OLE DB/ODBC</span></span>  
  
 <span data-ttu-id="d7072-119">**Origens multidimensionais**</span><span class="sxs-lookup"><span data-stu-id="d7072-119">**Multidimensional Sources**</span></span>  
  
-   <span data-ttu-id="d7072-120">Cubo do Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d7072-120">Microsoft SQL Server Analysis Services cube</span></span>  
  
 <span data-ttu-id="d7072-121">O Assistente de Importação de Tabela não dá suporte a importação de dados de uma Pasta de trabalho do [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d7072-121">The Table Import Wizard does not support importing data from a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Workbook as a data source.</span></span>  
  
### <a name="to-import-data-from-a-database"></a><span data-ttu-id="d7072-122">Para importar dados de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="d7072-122">To import data from a database</span></span>  
  
1.  <span data-ttu-id="d7072-123">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique no menu **Modelo** e em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="d7072-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="d7072-124">Na página **Conectar com uma Fonte de Dados** , selecione o tipo de banco de dados ao qual se conectar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d7072-124">On the **Connect to a Data Source** page, select the type of database to connect to, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="d7072-125">Siga as etapas no Assistente de Importação de Tabela.</span><span class="sxs-lookup"><span data-stu-id="d7072-125">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="d7072-126">Nas páginas subsequentes, você poderá selecionar tabelas específicas e exibições ou aplicar filtros usando a página **Selecionar Tabelas e Exibições** ou criando uma consulta SQL na página **Especificar uma Consulta SQL** .</span><span class="sxs-lookup"><span data-stu-id="d7072-126">On subsequent pages, you will be able to select specific tables and views or apply filters by using the **Select Tables and Views** page or by creating a SQL query on **Specify a SQL Query** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7072-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7072-127">See Also</span></span>  
 <span data-ttu-id="d7072-128">[Importar dados &#40;SSAS de tabela&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d7072-128">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="d7072-129">Fontes de dados com suporte &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="d7072-129">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  

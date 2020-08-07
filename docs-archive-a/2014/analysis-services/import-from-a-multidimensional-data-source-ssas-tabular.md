---
title: Importar de uma fonte de dados multidimensional (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7f0793ea-a4c7-42e9-b722-2164a454ebca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b26cc8ed7237f87fa5e23c6a2fd47e18de2c165
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583221"
---
# <a name="import-from-a-multidimensional-data-source-ssas-tabular"></a><span data-ttu-id="550ef-102">Importar de uma fonte de dados multidimensional (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="550ef-102">Import from a Multidimensional Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="550ef-103">Você pode usar um banco de dados de cubo do Analysis Services como uma fonte de dados para um modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="550ef-103">You can use an Analysis Services cube database as a data source for a tabular model.</span></span> <span data-ttu-id="550ef-104">Para importar dados de um cubo do Analysis Services, você deve definir uma Consulta MDX para selecionar dados para importar.</span><span class="sxs-lookup"><span data-stu-id="550ef-104">In order to import data from an Analysis Services cube, you must define an MDX Query to select data to import.</span></span>  
  
 <span data-ttu-id="550ef-105">Quaisquer dados contidos em um banco de dados do SQL Server Analysis Services pode ser importado para um modelo.</span><span class="sxs-lookup"><span data-stu-id="550ef-105">Any data that is contained in a SQL Server Analysis Services database can be imported into a model.</span></span> <span data-ttu-id="550ef-106">É possível extrair total ou parcialmente uma dimensão, ou obter fatias e agregações do cubo, como soma das vendas, mês a mês, durante o ano atual, etc. Porém, você deveria se lembrar de que todos os dados que você importa de um cubo são bidimensionais.</span><span class="sxs-lookup"><span data-stu-id="550ef-106">You can extract all or part of a dimension, or get slices and aggregates from the cube, such as the sum of sales, month by month, for the current year, etc. However, you should keep in mind all data that you import from a cube is flattened.</span></span> <span data-ttu-id="550ef-107">Portanto, se você definir uma consulta que recupera medidas ao longo de várias dimensões, os dados serão importados com cada dimensão em uma coluna separada.</span><span class="sxs-lookup"><span data-stu-id="550ef-107">Therefore, if you define a query that retrieves measures along multiple dimensions, the data will be imported with each dimension in a separate column.</span></span>  
  
 <span data-ttu-id="550ef-108">Os cubos do Analysis Services devem ter a versão do SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]ou [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="550ef-108">Analysis Services cubes must be version SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
### <a name="to-import-data-from-an-analysis-services-cube"></a><span data-ttu-id="550ef-109">Para importar dados de um cubo do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="550ef-109">To import data from an Analysis Services cube</span></span>  
  
1.  <span data-ttu-id="550ef-110">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique no menu **Modelo** e em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="550ef-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="550ef-111">Na página **Conectar com uma Fonte de Dados** , selecione **Microsoft Analysis Services**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="550ef-111">On the **Connect to a Data Source** page, select **Microsoft Analysis Services**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="550ef-112">Siga as etapas no Assistente de Importação de Tabela.</span><span class="sxs-lookup"><span data-stu-id="550ef-112">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="550ef-113">Você poderá especificar uma consulta MDX na página **Especificar uma Consulta MDX** .</span><span class="sxs-lookup"><span data-stu-id="550ef-113">You will be able to specify an MDX query on the **Specify a MDX Query** page.</span></span> <span data-ttu-id="550ef-114">Para usar o Designer de Consulta MDX, na página Especificar uma Consulta MDX, clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="550ef-114">To use the MDX Query Designer, on the Specify a MDX Query page, click **Design**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="550ef-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="550ef-115">See Also</span></span>  
 <span data-ttu-id="550ef-116">[Importar dados &#40;SSAS de tabela&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="550ef-116">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="550ef-117">Fontes de dados com suporte &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="550ef-117">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  

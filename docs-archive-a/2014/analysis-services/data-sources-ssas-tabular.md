---
title: Fontes de dados (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6908998b-9302-4a90-976e-770106b48d18
author: minewiskan
ms.author: owend
ms.openlocfilehash: d686d8100e30d7608e8d90f135022bdf46785723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681256"
---
# <a name="data-sources-ssas-tabular"></a><span data-ttu-id="a9818-102">Fontes de Dados (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="a9818-102">Data Sources (SSAS Tabular)</span></span>
  <span data-ttu-id="a9818-103">Fontes de dados fornecem os dados a serem incluídos em uma solução modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="a9818-103">Data sources provide the data to be included in a tabular model solution.</span></span> <span data-ttu-id="a9818-104">Você pode importar dados em seu modelo de uma ampla variedade de origens como bancos de dados relacionais, feeds de dados, fontes de dados multidimensionais como um cubo do Analysis Services, e de arquivos de texto como uma pasta de trabalho do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="a9818-104">You can import data into your model from a wide variety of sources such as relational databases, data feeds, multidimensional data sources such as an Analysis Services cube, and from text files such as a Microsoft Excel workbook.</span></span> <span data-ttu-id="a9818-105">Os tópicos nesta seção fornecem informações sobre os tipos de fontes de dados de que você pode importar, os vários tipos de dados que você pode importar e tarefas que descrevem como importar dados dessas fontes.</span><span class="sxs-lookup"><span data-stu-id="a9818-105">Topics in this section provide information about the types of data sources you can import from, the various data types you can import, and tasks describing how to import data from those sources.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="a9818-106">Tópicos relacionados e tarefas</span><span class="sxs-lookup"><span data-stu-id="a9818-106">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="a9818-107">Tópico</span><span class="sxs-lookup"><span data-stu-id="a9818-107">Topic</span></span>|<span data-ttu-id="a9818-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="a9818-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a9818-109">Fontes de dados com suporte &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="a9818-109">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)|<span data-ttu-id="a9818-110">Este tópico fornece informações sobre as fontes de dados diferentes de que você pode importar dados.</span><span class="sxs-lookup"><span data-stu-id="a9818-110">This topic provides information about the different data sources that you can import data from.</span></span>|  
|[<span data-ttu-id="a9818-111">Tipos de dados com suporte &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="a9818-111">Data Types Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-types-supported-ssas-tabular.md)|<span data-ttu-id="a9818-112">Este tópico fornece informações sobre os vários tipos de dados que têm suporte em um Modelo Tabular.</span><span class="sxs-lookup"><span data-stu-id="a9818-112">This topic provides information about the various data types that are supported in a Tabular Model.</span></span>|  
|[<span data-ttu-id="a9818-113">Representação &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="a9818-113">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)|<span data-ttu-id="a9818-114">Este tópico fornece informações sobre representação, que fornece credenciais de logon que são usadas pelo Analysis Services ao conectar-se a uma fonte de dados para importar e atualizar dados.</span><span class="sxs-lookup"><span data-stu-id="a9818-114">This topic provides information about impersonation, which provides logon credentials that are used by Analysis Services when connecting to a data source to import and refresh data.</span></span>|  
|[<span data-ttu-id="a9818-115">Importar dados &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="a9818-115">Import Data &#40;SSAS Tabular&#41;</span></span>](import-data-ssas-tabular.md)|<span data-ttu-id="a9818-116">As tarefas nesta seção descrevem como importar dados de fontes de dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="a9818-116">Tasks in this section describe how to import data from different data sources.</span></span>|  
|[<span data-ttu-id="a9818-117">Processar dados &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="a9818-117">Process Data &#40;SSAS Tabular&#41;</span></span>](process-data-ssas-tabular.md)|<span data-ttu-id="a9818-118">As tarefas nesta seção descrevem como processar (atualizar) ou alterar dados que já foram importados em um modelo.</span><span class="sxs-lookup"><span data-stu-id="a9818-118">Tasks in this section describe how to process (refresh) or change data that has already been imported into a model.</span></span>|  
|[<span data-ttu-id="a9818-119">Editar uma conexão de fonte de dados existente &#40;SSAS Tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="a9818-119">Edit an Existing Data Source Connection &#40;SSAS Tabular&#41;</span></span>](edit-an-existing-data-source-connection-ssas-tabular.md)|<span data-ttu-id="a9818-120">Descreve como editar a conexão da fonte de dados que já foi criada e usada para importar dados de uma origem.</span><span class="sxs-lookup"><span data-stu-id="a9818-120">Describes how to edit a data source connection that has already been created and used to import data from a source.</span></span>|  
  
  

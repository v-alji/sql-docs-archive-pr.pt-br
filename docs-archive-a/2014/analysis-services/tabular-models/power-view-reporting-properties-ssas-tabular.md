---
title: Power View Propriedades de relatório (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 51205c2d-b6ce-4b92-afd2-58e399a81691
author: minewiskan
ms.author: owend
ms.openlocfilehash: e85d91578e5c3f4b47f56eeb86aa738e37e8f59b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679003"
---
# <a name="power-view-reporting-properties-ssas-tabular"></a><span data-ttu-id="9e5aa-102">Propriedades de relatório de Power View (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="9e5aa-102">Power View Reporting Properties (SSAS Tabular)</span></span>
  [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="9e5aa-103">oferece relatórios ad hoc intuitivos para usuários comerciais, tais como analistas de dados, tomadores de decisões de negócios e operadores de informações.</span><span class="sxs-lookup"><span data-stu-id="9e5aa-103">provides intuitive ad-hoc reporting for business users such as data analysts, business decision makers, and information workers.</span></span> <span data-ttu-id="9e5aa-104">Eles podem criar e interagir facilmente com exibição de dados de modelos tabulares com base em pastas de trabalho PowerPivot publicadas em uma Galeria do PowerPivot ou modelos de tabela criados usando o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e, em seguida, implantados em instâncias do Analysis Services do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e5aa-104">They can easily create and interact with views of data from tabular models based on PowerPivot workbooks published in a PowerPivot Gallery, or tabular models authored by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and then deployed to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Analysis Services instances.</span></span> [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="9e5aa-105">é um aplicativo do Silverlight baseado no navegador, iniciado no SharePoint Server 2010 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="9e5aa-105">is a browser-based Silverlight application launched from SharePoint Server 2010 or later.</span></span>  
  
 <span data-ttu-id="9e5aa-106">Ao criar projetos de modelo tabular no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], você pode configurar determinadas propriedades de relatório exclusivas para relatórios do [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e5aa-106">When authoring tabular model projects in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can configure certain reporting properties unique to [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="9e5aa-107">Os tópicos nesta seção descrevem como otimizar um modelo para melhorar a experiência de relatórios no [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e5aa-107">Topics in this section describe how to optimize a model to improve the reporting experience in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9e5aa-108">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="9e5aa-108">Related Tasks</span></span>  
  
|<span data-ttu-id="9e5aa-109">Tópico</span><span class="sxs-lookup"><span data-stu-id="9e5aa-109">Topic</span></span>|<span data-ttu-id="9e5aa-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e5aa-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9e5aa-111">Configurar conjunto de campo padrão para relatórios de Power View &#40;SSAS Tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="9e5aa-111">Configure Default Field Set for Power View Reports &#40;SSAS Tabular&#41;</span></span>](power-view-configure-default-field-set-for-reports.md)|<span data-ttu-id="9e5aa-112">Descreve como configurar um Conjunto de Campo Padrão; uma lista predefinida de colunas e medidas que são adicionadas automaticamente a uma tela de relatório do [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] quando a tabela é selecionada na lista de campos de relatório.</span><span class="sxs-lookup"><span data-stu-id="9e5aa-112">Describes how to configure a Default Field Set; a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span>|  
|[<span data-ttu-id="9e5aa-113">Configurar propriedades de comportamento de tabela para relatórios de Power View &#40;SSAS Tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="9e5aa-113">Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;</span></span>](power-view-configure-table-behavior-properties-for-reports.md)|<span data-ttu-id="9e5aa-114">Descreve como configurar as propriedades de comportamento da tabela que expõem linhas de detalhes um nível mais granular.</span><span class="sxs-lookup"><span data-stu-id="9e5aa-114">Describes how to configure table behavior properties that expose detail rows at a more granular level.</span></span> <span data-ttu-id="9e5aa-115">Definir as propriedades do comportamento da tabela altera o comportamento do agrupamento das linhas de detalhes e produz uma melhor colocação padrão de identificação de informações em layouts de peça, cartão e gráfico.</span><span class="sxs-lookup"><span data-stu-id="9e5aa-115">Setting table behavior properties changes the grouping behavior of detail rows and produces a better default placement of identifying information in tile, card, and chart layouts.</span></span>|  
  
  

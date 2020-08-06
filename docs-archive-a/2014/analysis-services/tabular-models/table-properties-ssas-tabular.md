---
title: Propriedades da tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9613609c42de8fd3a4aab7aec3208dfe3d31be4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684359"
---
# <a name="table-properties-ssas-tabular"></a><span data-ttu-id="37d28-102">Propriedades da tabela (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="37d28-102">Table Properties (SSAS Tabular)</span></span>
  <span data-ttu-id="37d28-103">Este tópico descreve as propriedades do modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="37d28-103">This topic describes tabular model table properties.</span></span> <span data-ttu-id="37d28-104">As propriedades descritas aqui são diferentes daquelas na caixa de diálogo Editar Propriedades de Tabela, que definem quais colunas da origem são importadas.</span><span class="sxs-lookup"><span data-stu-id="37d28-104">The properties described here are different from those in the Edit Table Properties dialog box, which define which columns from the source are imported.</span></span>  
  
 <span data-ttu-id="37d28-105">Seções neste tópico:</span><span class="sxs-lookup"><span data-stu-id="37d28-105">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="37d28-106">Propriedades da tabela</span><span class="sxs-lookup"><span data-stu-id="37d28-106">Table Properties</span></span>](#bkmk_properties)  
  
-   [<span data-ttu-id="37d28-107">Para definir as configurações de propriedade da tabela</span><span class="sxs-lookup"><span data-stu-id="37d28-107">To configure table property settings</span></span>](#bkmk_config_prop)  
  
##  <a name="table-properties"></a><a name="bkmk_properties"></a><span data-ttu-id="37d28-108">Propriedades da tabela</span><span class="sxs-lookup"><span data-stu-id="37d28-108">Table Properties</span></span>  
 <span data-ttu-id="37d28-109">**Basic**</span><span class="sxs-lookup"><span data-stu-id="37d28-109">**Basic**</span></span>  
  
|<span data-ttu-id="37d28-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="37d28-110">Property</span></span>|<span data-ttu-id="37d28-111">Configuração padrão</span><span class="sxs-lookup"><span data-stu-id="37d28-111">Default Setting</span></span>|<span data-ttu-id="37d28-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="37d28-112">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="37d28-113">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="37d28-113">**Connection Name**</span></span>|\<connection name>|<span data-ttu-id="37d28-114">O nome da conexão com a fonte de dados da tabela.</span><span class="sxs-lookup"><span data-stu-id="37d28-114">The name of the connection to the table's data source.</span></span><br /><br /> <span data-ttu-id="37d28-115">Para editar a conexão, clique no botão.</span><span class="sxs-lookup"><span data-stu-id="37d28-115">To edit the connection, click the button.</span></span>|  
|<span data-ttu-id="37d28-116">**Oculto**</span><span class="sxs-lookup"><span data-stu-id="37d28-116">**Hidden**</span></span>|<span data-ttu-id="37d28-117">Falso</span><span class="sxs-lookup"><span data-stu-id="37d28-117">False</span></span>|<span data-ttu-id="37d28-118">Especifica se a tabela é ocultada das listas de campo de cliente de relatório.</span><span class="sxs-lookup"><span data-stu-id="37d28-118">Specifies whether the table is hidden from reporting client field lists.</span></span>|  
|<span data-ttu-id="37d28-119">**Partições**</span><span class="sxs-lookup"><span data-stu-id="37d28-119">**Partitions**</span></span>||<span data-ttu-id="37d28-120">As partições para a tabela não podem ser exibidas na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="37d28-120">Partitions for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="37d28-121">Para exibir, criar ou editar partições, clique no botão para abrir o Gerenciador de Partições.</span><span class="sxs-lookup"><span data-stu-id="37d28-121">To view, create, or edit partitions, click the button to open the Partition Manager.</span></span>|  
|<span data-ttu-id="37d28-122">**Dados de origem**</span><span class="sxs-lookup"><span data-stu-id="37d28-122">**Source Data**</span></span>||<span data-ttu-id="37d28-123">Os dados de origem da tabela não podem ser exibidos na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="37d28-123">Source data for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="37d28-124">Para exibir ou editar os dados de origem, clique no botão para abrir a caixa de diálogo Editar Propriedades da Tabela.</span><span class="sxs-lookup"><span data-stu-id="37d28-124">To view or edit the source data, click the button to open the Edit Table Properties dialog box.</span></span>|  
|<span data-ttu-id="37d28-125">**Descrição da tabela**</span><span class="sxs-lookup"><span data-stu-id="37d28-125">**Table Description**</span></span>||<span data-ttu-id="37d28-126">Uma descrição de texto da tabela.</span><span class="sxs-lookup"><span data-stu-id="37d28-126">A text description for the table.</span></span><br /><br /> <span data-ttu-id="37d28-127">No [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], se um usuário final colocar o cursor sobre esta tabela na lista de campos, a descrição aparecerá como uma dica de ferramenta.</span><span class="sxs-lookup"><span data-stu-id="37d28-127">In [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], if an end-user places the cursor over this table in the field list, the description appears as a tooltip.</span></span>|  
|<span data-ttu-id="37d28-128">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="37d28-128">**Table Name**</span></span>|\<friendly name>|<span data-ttu-id="37d28-129">Especifica o nome amigável da tabela.</span><span class="sxs-lookup"><span data-stu-id="37d28-129">Specifies the table's friendly name.</span></span> <span data-ttu-id="37d28-130">O nome da tabela pode ser especificado quando uma tabela é importada com o uso do Assistente de Importação de Tabela ou a qualquer momento após a importação.</span><span class="sxs-lookup"><span data-stu-id="37d28-130">The table name can be specified when a table is imported using the Table Import Wizard or at any time after import.</span></span> <span data-ttu-id="37d28-131">O nome da tabela no modelo pode ser diferente da tabela associada na origem.</span><span class="sxs-lookup"><span data-stu-id="37d28-131">The table name in the model can be different from the associated table at the source.</span></span> <span data-ttu-id="37d28-132">O nome amigável da tabela aparece na lista de campos do aplicativo cliente de relatório e no banco de dados modelo no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37d28-132">The table friendly name appears in the reporting client application field list as well as in the model database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|  
  
 <span data-ttu-id="37d28-133">**Propriedades de relatório**</span><span class="sxs-lookup"><span data-stu-id="37d28-133">**Reporting Properties**</span></span>  
  
 <span data-ttu-id="37d28-134">Para obter descrições detalhadas e informações de configuração das propriedades de relatório, consulte [Propriedades de relatório do Power View &#40;SSAS de Tabela&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="37d28-134">For detailed descriptions and configuration information for reporting properties, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
|<span data-ttu-id="37d28-135">Propriedade</span><span class="sxs-lookup"><span data-stu-id="37d28-135">Property</span></span>|<span data-ttu-id="37d28-136">Configuração padrão</span><span class="sxs-lookup"><span data-stu-id="37d28-136">Default Setting</span></span>|<span data-ttu-id="37d28-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="37d28-137">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="37d28-138">**Conjunto de Campos Padrão**</span><span class="sxs-lookup"><span data-stu-id="37d28-138">**Default Field Set**</span></span>|||  
|<span data-ttu-id="37d28-139">Comportamento de tabela</span><span class="sxs-lookup"><span data-stu-id="37d28-139">Table Behavior</span></span>|||  
  
###  <a name="to-configure-table-property-settings"></a><a name="bkmk_config_prop"></a><span data-ttu-id="37d28-140">Para definir as configurações de propriedade da tabela</span><span class="sxs-lookup"><span data-stu-id="37d28-140">To configure table property settings</span></span>  
  
1.  <span data-ttu-id="37d28-141">No designer de modelos, na Exibição de Dados, clique em uma tabela (guia) ou, na Exibição de Diagrama, clique em um cabeçalho de tabela.</span><span class="sxs-lookup"><span data-stu-id="37d28-141">In the model designer, in Data View, click a table (tab), or, in Diagram View, click a table header.</span></span>  
  
2.  <span data-ttu-id="37d28-142">Na janela **Propriedades** , clique em uma propriedade e digite um valor ou clique no botão para obter opções de configuração adicionais.</span><span class="sxs-lookup"><span data-stu-id="37d28-142">In the **Properties** window, click on a property, and then type a value or click the button for additional configuration options.</span></span>  
  
  

---
title: Especificar tipos de tabela (Assistente de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytabletypes.f1
ms.assetid: 8209a707-faef-4ffc-8991-6c13bb350753
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88c09f26958c37ed0a99efb54a5eb5c08505d16b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581492"
---
# <a name="specify-table-types-data-mining-wizard"></a><span data-ttu-id="05a59-102">Especificar tipos de tabelas (Assistente de Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="05a59-102">Specify Table Types (Data Mining Wizard)</span></span>
  <span data-ttu-id="05a59-103">Use a página **Especificar Tipos de Tabelas** para identificar as tabelas a serem usadas para definir a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="05a59-103">Use the **Specify Table Types** page to identify the tables to use to define the mining structure.</span></span> <span data-ttu-id="05a59-104">Se uma tabela não for selecionada, ela não será usada para definir a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="05a59-104">If a table is not selected, it will not be used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05a59-105">Você pode adicionar tabelas mais tarde na guia **Estrutura de Mineração** do **Designer de Data Mining**.</span><span class="sxs-lookup"><span data-stu-id="05a59-105">You can add tables later from the **Mining Structure** tab in **Data Mining Designer**.</span></span>  
  
 <span data-ttu-id="05a59-106">**Para obter mais informações:** [Tabelas Aninhadas &#40;Analysis Services – Data mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Assistente de Data Mining &#40;Analysis Services – Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md) e [Criar uma estrutura de mineração relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="05a59-106">**For More Information:** [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="05a59-107">Opções</span><span class="sxs-lookup"><span data-stu-id="05a59-107">Options</span></span>  
 <span data-ttu-id="05a59-108">**Tabelas**</span><span class="sxs-lookup"><span data-stu-id="05a59-108">**Tables**</span></span>  
 <span data-ttu-id="05a59-109">Exibe as tabelas na exibição da fonte de dados selecionada na página **Selecionar Exibição da Fonte de Dados** do assistente.</span><span class="sxs-lookup"><span data-stu-id="05a59-109">Displays the tables in the data source view that you selected on the **Select Data Source View** page of the wizard.</span></span>  
  
 <span data-ttu-id="05a59-110">**Casos**</span><span class="sxs-lookup"><span data-stu-id="05a59-110">**Case**</span></span>  
 <span data-ttu-id="05a59-111">Selecione uma tabela a ser usada como a tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="05a59-111">Select one table to use as the case table.</span></span>  
  
 <span data-ttu-id="05a59-112">**Aninhado**</span><span class="sxs-lookup"><span data-stu-id="05a59-112">**Nested**</span></span>  
 <span data-ttu-id="05a59-113">Selecione as tabelas a serem usadas como tabelas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="05a59-113">Select the tables to use as nested tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05a59-114">Essas tabelas devem ter uma relação de muitos para um com a tabela de casos e não uma relação de um para muitos.</span><span class="sxs-lookup"><span data-stu-id="05a59-114">These tables must have a many-to-one relationship with the case table, not a one-to-many relationship.</span></span> <span data-ttu-id="05a59-115">Você deve especificar essa relação na exibição da fonte de dados para poder selecionar a tabela como aninhada.</span><span class="sxs-lookup"><span data-stu-id="05a59-115">You must specify this relationship in the data source view before you can select the table as nested.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05a59-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05a59-116">See Also</span></span>  
 <span data-ttu-id="05a59-117">[Ajuda F1 do assistente de mineração de dados &#40;Analysis Services Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="05a59-117">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="05a59-118">[Selecione exibição da fonte de dados &#40;assistente de mineração de dados&#41;](select-data-source-view-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="05a59-118">[Select Data Source View &#40;Data Mining Wizard&#41;](select-data-source-view-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="05a59-119">Especifique os dados de treinamento &#40;assistente de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="05a59-119">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  

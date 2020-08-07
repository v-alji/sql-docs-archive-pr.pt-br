---
title: Escolha como importar os dados (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.choosehowtoimpdata.f1
ms.assetid: 17dc6903-c239-46aa-a3b0-6e3156accacc
author: minewiskan
ms.author: owend
ms.openlocfilehash: fba1d5801f325400b228920fffa06512f4db8de2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571704"
---
# <a name="choose-how-to-import-the-data-ssas"></a><span data-ttu-id="019de-102">Escolher como importar os dados (SSAS)</span><span class="sxs-lookup"><span data-stu-id="019de-102">Choose How to Import the Data (SSAS)</span></span>
  <span data-ttu-id="019de-103">Esta página do **Assistente de Importação de Tabela** permite escolher como importar dados da fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="019de-103">This page of the **Table Import Wizard** enables you to choose how to import data from the selected data source.</span></span> <span data-ttu-id="019de-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="019de-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="019de-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="019de-105">UI element list</span></span>  
 <span data-ttu-id="019de-106">**Selecionar itens em uma lista de tabelas e exibições para escolher os dados a serem importados**</span><span class="sxs-lookup"><span data-stu-id="019de-106">**Select from a list of tables and views to choose the data to import**</span></span>  
 <span data-ttu-id="019de-107">Selecione esta opção se desejar importar dados selecionando em uma lista.</span><span class="sxs-lookup"><span data-stu-id="019de-107">Select this option if you want to import data by selecting from a list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="019de-108">Esta opção só está disponível quando a fonte de dados selecionada expõe as informações de esquema com suporte no **Assistente de Importação de Tabela** .</span><span class="sxs-lookup"><span data-stu-id="019de-108">This option is available only when the selected data source exposes schema information that the **Table Import Wizard** supports.</span></span>  
  
 <span data-ttu-id="019de-109">**Escrever uma consulta para especificar os dados a serem importados**</span><span class="sxs-lookup"><span data-stu-id="019de-109">**Write a query to specify the data to import**</span></span>  
 <span data-ttu-id="019de-110">Selecione esta opção se quiser importar dados usando uma consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="019de-110">Select this option if you want to import data by using a SQL query.</span></span> <span data-ttu-id="019de-111">A consulta SQL pode manipular os dados que são importados.</span><span class="sxs-lookup"><span data-stu-id="019de-111">The SQL query can manipulate the data that is imported.</span></span> <span data-ttu-id="019de-112">Por exemplo, é possível unir dados de tabelas diferentes ou selecionar apenas linhas que atendam a certos critérios.</span><span class="sxs-lookup"><span data-stu-id="019de-112">For example, you could join data from different tables or select only rows that meet certain criteria.</span></span>  
  
  

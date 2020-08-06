---
title: Referência de interface do usuário da caixa de diálogo Sugerir Tipos de Coluna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.suggestdatatypes.f1
ms.assetid: 8d5652e0-cf57-483f-828b-10f00c08418b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbca2a3186a58b1148eb9627825fdfddf334339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685236"
---
# <a name="suggest-column-types-dialog-box-ui-reference"></a><span data-ttu-id="fe994-102">Referência da interface do usuário da caixa de diálogo Sugerir Tipos de Coluna</span><span class="sxs-lookup"><span data-stu-id="fe994-102">Suggest Column Types Dialog Box UI Reference</span></span>
  <span data-ttu-id="fe994-103">Use a caixa de diálogo **Sugerir Tipos de Coluna** para identificar o tipo de dados e o tamanho das colunas em um Gerenciador de Conexões de Arquivos Simples, com base em uma amostragem do conteúdo dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="fe994-103">Use the **Suggest Column Types** dialog box to identify the data type and length of columns in a Flat File Connection Manager based on a sampling of the file content.</span></span>  
  
 <span data-ttu-id="fe994-104">Para saber mais sobre os tipos de dados usados pelo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fe994-104">To learn more about the data types used by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fe994-105">Opções</span><span class="sxs-lookup"><span data-stu-id="fe994-105">Options</span></span>  
 <span data-ttu-id="fe994-106">**Número de linhas**</span><span class="sxs-lookup"><span data-stu-id="fe994-106">**Number of rows**</span></span>  
 <span data-ttu-id="fe994-107">Digite ou selecione o número de linhas na amostra que o algoritmo usa.</span><span class="sxs-lookup"><span data-stu-id="fe994-107">Type or select the number of rows in the sample that the algorithm uses.</span></span>  
  
 <span data-ttu-id="fe994-108">**Sugerir o menor tipo de dados inteiros**</span><span class="sxs-lookup"><span data-stu-id="fe994-108">**Suggest the smallest integer data type**</span></span>  
 <span data-ttu-id="fe994-109">Desmarque esta caixa de seleção para ignorar a avaliação.</span><span class="sxs-lookup"><span data-stu-id="fe994-109">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="fe994-110">Se selecionada, determina o menor tipo de dados inteiro possível para colunas que contêm dados numéricos integrais.</span><span class="sxs-lookup"><span data-stu-id="fe994-110">If selected, determines the smallest possible integer data type for columns that contain integral numeric data.</span></span>  
  
 <span data-ttu-id="fe994-111">**Sugerir o menor tipo de dados reais**</span><span class="sxs-lookup"><span data-stu-id="fe994-111">**Suggest the smallest real data type**</span></span>  
 <span data-ttu-id="fe994-112">Desmarque esta caixa de seleção para ignorar a avaliação.</span><span class="sxs-lookup"><span data-stu-id="fe994-112">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="fe994-113">Se selecionada, determina se as colunas que contêm dados numéricos reais podem usar o menor tipo de dados reais, DT_R4.</span><span class="sxs-lookup"><span data-stu-id="fe994-113">If selected, determines whether columns that contain real numeric data can use the smaller real data type, DT_R4.</span></span>  
  
 <span data-ttu-id="fe994-114">**Identificar colunas de Boolianos usando os seguintes valores**</span><span class="sxs-lookup"><span data-stu-id="fe994-114">**Identify Boolean columns using the following values**</span></span>  
 <span data-ttu-id="fe994-115">Digite os dois valores que deseja usar como valores Boolianos verdadeiro e falso.</span><span class="sxs-lookup"><span data-stu-id="fe994-115">Type the two values that you want to use as the Boolean values true and false.</span></span> <span data-ttu-id="fe994-116">Os valores devem ser separados por uma vírgula, com o primeiro valor representando Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="fe994-116">The values must be separated by a comma, and the first value represents True.</span></span>  
  
 <span data-ttu-id="fe994-117">**Preencher colunas de cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="fe994-117">**Pad string columns**</span></span>  
 <span data-ttu-id="fe994-118">Marque esta caixa de seleção para habilitar o preenchimento da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fe994-118">Select this check box to enable string padding.</span></span>  
  
 <span data-ttu-id="fe994-119">**Porcentagem de enchimento**</span><span class="sxs-lookup"><span data-stu-id="fe994-119">**Percent padding**</span></span>  
 <span data-ttu-id="fe994-120">Digite ou selecione a porcentagem pela qual aumentar o tamanho de coluna para tipos de dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fe994-120">Type or select the percentage of the column lengths by which to increase the length of columns for character data types.</span></span> <span data-ttu-id="fe994-121">A porcentagem deve ser um inteiro.</span><span class="sxs-lookup"><span data-stu-id="fe994-121">The percentage must be an integer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe994-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe994-122">See Also</span></span>  
 <span data-ttu-id="fe994-123">[Referência de mensagens e erros do Integration Services](../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fe994-123">[Integration Services Error and Message Reference](../integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="fe994-124">Gerenciador de Conexões de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="fe994-124">Flat File Connection Manager</span></span>](file-connection-manager.md)  
  
  

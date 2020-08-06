---
title: Editor de transformação Union All | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltransformation.f1
helpviewer_keywords:
- Union All Transformation Editor
ms.assetid: 32fbc1c1-da83-4684-9479-31fc3e2df98c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7e84c106767aa897b2e419b51ca5b5c538501cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570745"
---
# <a name="union-all-transformation-editor"></a><span data-ttu-id="a4cc2-102">Editor de Transformação Union All</span><span class="sxs-lookup"><span data-stu-id="a4cc2-102">Union All Transformation Editor</span></span>
  <span data-ttu-id="a4cc2-103">Use a caixa de diálogo **Editor de Transformação Union All** para mesclar vários conjuntos de linhas de entrada em um único conjunto de linhas de saída.</span><span class="sxs-lookup"><span data-stu-id="a4cc2-103">Use the **Union All Transformation Editor** dialog box to merge several input rowsets into a single output rowset.</span></span> <span data-ttu-id="a4cc2-104">Incluindo a transformação Union All em um fluxo de dados, é possível mesclar dados de vários fluxos de dados, criar conjuntos de dados complexos aninhando transformações Union All e mesclar as linhas novamente após corrigir erros nos dados.</span><span class="sxs-lookup"><span data-stu-id="a4cc2-104">By including the Union All transformation in a data flow, you can merge data from multiple data flows, create complex datasets by nesting Union All transformations, and re-merge rows after you correct errors in the data.</span></span>  
  
 <span data-ttu-id="a4cc2-105">Para saber mais sobre a transformação Union All, consulte [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a4cc2-105">To learn more about the Union All transformation, see [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4cc2-106">Opções</span><span class="sxs-lookup"><span data-stu-id="a4cc2-106">Options</span></span>  
 <span data-ttu-id="a4cc2-107">**Nome da Coluna de Saída**</span><span class="sxs-lookup"><span data-stu-id="a4cc2-107">**Output Column Name**</span></span>  
 <span data-ttu-id="a4cc2-108">Digite um alias para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="a4cc2-108">Type an alias for each column.</span></span> <span data-ttu-id="a4cc2-109">O padrão é o nome da coluna de entrada da primeira entrada (referência); contudo, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="a4cc2-109">The default is the name of the input column from the first (reference) input; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="a4cc2-110">**Union All Entrada 1**</span><span class="sxs-lookup"><span data-stu-id="a4cc2-110">**Union All Input 1**</span></span>  
 <span data-ttu-id="a4cc2-111">Selecione a partir da lista de colunas de entrada disponíveis na primeira entrada (referência).</span><span class="sxs-lookup"><span data-stu-id="a4cc2-111">Select from the list of available input columns in the first (reference) input.</span></span> <span data-ttu-id="a4cc2-112">Os metadados das colunas mapeadas devem ser correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a4cc2-112">The metadata of mapped columns must match.</span></span>  
  
 <span data-ttu-id="a4cc2-113">**Union All Entrada n**</span><span class="sxs-lookup"><span data-stu-id="a4cc2-113">**Union All Input n**</span></span>  
 <span data-ttu-id="a4cc2-114">Selecione a partir da lista de colunas de entrada disponíveis na segunda entrada e adicionais.</span><span class="sxs-lookup"><span data-stu-id="a4cc2-114">Select from the list of available input columns in the second and additional inputs.</span></span> <span data-ttu-id="a4cc2-115">Os metadados das colunas mapeadas devem ser correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a4cc2-115">The metadata of mapped columns must match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4cc2-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4cc2-116">See Also</span></span>  
 <span data-ttu-id="a4cc2-117">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a4cc2-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a4cc2-118">[Mesclar dados usando a transformação Union All](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a4cc2-118">[Merge Data by Using the Union All Transformation](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span></span>  
 <span data-ttu-id="a4cc2-119">[Transformação Mesclar](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a4cc2-119">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="a4cc2-120">Transformação Junção de Mesclagem</span><span class="sxs-lookup"><span data-stu-id="a4cc2-120">Merge Join Transformation</span></span>](data-flow/transformations/merge-join-transformation.md)  
  
  

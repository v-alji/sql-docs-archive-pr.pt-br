---
title: Editor Resolver Referência de Coluna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.resolvereferences.mapper.F1
- sql12.dts.designer.resolvereferences.preview.F1
ms.assetid: bb3ee33c-79c4-4c76-a82f-71581b4a60f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 600b6f4d5ec12290d654f0854cc548a5bbcf4335
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574821"
---
# <a name="resolve-column-reference-editor"></a><span data-ttu-id="15a7b-102">Resolver editor de referência de coluna</span><span class="sxs-lookup"><span data-stu-id="15a7b-102">Resolve Column Reference Editor</span></span>
  <span data-ttu-id="15a7b-103">Quando um caminho de entrada é desconectado ou se houver qualquer coluna não mapeada no caminho, um ícone de erro será exibido ao lado do caminho de dados correspondente.</span><span class="sxs-lookup"><span data-stu-id="15a7b-103">When an input path is disconnected or if there are any unmapped columns in the path, an error icon is displayed beside the corresponding data path.</span></span> <span data-ttu-id="15a7b-104">Para simplificar a resolução de erros de referência de coluna, o novo editor Resolver Referências permite vincular colunas de saída não mapeadas com colunas de entrada não mapeadas para todos os caminhos da árvore de execução.</span><span class="sxs-lookup"><span data-stu-id="15a7b-104">To simplify the resolution of column reference errors, the new Resolve References editor allows you to link unmapped output columns with unmapped input columns for all paths in the execution tree.</span></span> <span data-ttu-id="15a7b-105">O editor Resolver Referências também realçará os caminhos para indicar quais caminhos estão sendo resolvidos.</span><span class="sxs-lookup"><span data-stu-id="15a7b-105">The Resolve References editor will also highlight the paths to indicate which paths are being resolved.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15a7b-106">Agora é possível editar um componente até mesmo quando seu caminho de entrada está desconectado</span><span class="sxs-lookup"><span data-stu-id="15a7b-106">It is now possible to edit a component even when its input path is disconnected</span></span>  
  
 <span data-ttu-id="15a7b-107">Depois que todas as referências a coluna foram resolvidas, se não houver erros de caminho de dados, nenhum ícone de erro será exibido ao lado dos caminhos de dados.</span><span class="sxs-lookup"><span data-stu-id="15a7b-107">After all column references have been resolved, if there are no other data path errors, no error icons will be displayed beside the data paths.</span></span>  
  
## <a name="options"></a><span data-ttu-id="15a7b-108">Opções</span><span class="sxs-lookup"><span data-stu-id="15a7b-108">Options</span></span>  
 <span data-ttu-id="15a7b-109">Colunas de Saída Não Mapeadas (Origem):</span><span class="sxs-lookup"><span data-stu-id="15a7b-109">Unmapped Output Columns (Source):</span></span>  
 <span data-ttu-id="15a7b-110">Colunas do caminho upstream que não estão mapeadas no momento</span><span class="sxs-lookup"><span data-stu-id="15a7b-110">Columns from the upstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="15a7b-111">Colunas Mapeadas (Origem):</span><span class="sxs-lookup"><span data-stu-id="15a7b-111">Mapped Columns (Source):</span></span>  
 <span data-ttu-id="15a7b-112">Colunas do caminho upstream que estão mapeadas para colunas do caminho downstream</span><span class="sxs-lookup"><span data-stu-id="15a7b-112">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="15a7b-113">Colunas Mapeadas (Destino):</span><span class="sxs-lookup"><span data-stu-id="15a7b-113">Mapped Columns (Destination):</span></span>  
 <span data-ttu-id="15a7b-114">Colunas do caminho upstream que estão mapeadas para colunas do caminho downstream</span><span class="sxs-lookup"><span data-stu-id="15a7b-114">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="15a7b-115">Colunas de Entrada Não Mapeadas (Destino):</span><span class="sxs-lookup"><span data-stu-id="15a7b-115">Unmapped Input Columns (Destination):</span></span>  
 <span data-ttu-id="15a7b-116">Colunas do caminho downstream que não estão mapeadas no momento</span><span class="sxs-lookup"><span data-stu-id="15a7b-116">Columns from the downstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="15a7b-117">Excluir Colunas de Entrada Não Mapeadas</span><span class="sxs-lookup"><span data-stu-id="15a7b-117">Delete Unmapped Input Columns</span></span>  
 <span data-ttu-id="15a7b-118">Selecione Excluir Colunas de Entrada Não Mapeadas para ignorar colunas não mapeadas no destino do caminho de dados.</span><span class="sxs-lookup"><span data-stu-id="15a7b-118">Check Delete Unmapped Input Columns to ignore unmapped columns at the destination of the data path.</span></span> <span data-ttu-id="15a7b-119">O botão Visualizar Alterações exibe uma lista das alterações que ocorrerão quando você pressionar o botão OK.</span><span class="sxs-lookup"><span data-stu-id="15a7b-119">The Preview Changes button displays a list of the changes that will occur when you press the OK button.</span></span>  
  
  

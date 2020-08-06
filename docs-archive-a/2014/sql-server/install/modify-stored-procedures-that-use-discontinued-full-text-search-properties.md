---
title: Modificar procedimentos armazenados que usam Propriedades de pesquisa de texto completo descontinuadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- discontinued properties [Full-Text Search]
- stored procedures [Full-Text Search]
ms.assetid: 8d9392d9-a9ba-4378-84e4-59f516b67ddb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12262a588742f0e3be094e32a2a0208a85b6f28a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573475"
---
# <a name="modify-stored-procedures-that-use-discontinued-full-text-search-properties"></a><span data-ttu-id="b551f-102">Modificar procedimentos armazenados que usam propriedades de Pesquisa de Texto Completo descontinuadas</span><span class="sxs-lookup"><span data-stu-id="b551f-102">Modify stored procedures that use discontinued Full-Text Search properties</span></span>
  <span data-ttu-id="b551f-103">Para assegurar que seus procedimentos armazenados tenham o desempenho esperado, você deve editar procedimentos existentes e remover aquelas propriedades e configurações relacionadas a texto completo que foram removidas ou substituídas.</span><span class="sxs-lookup"><span data-stu-id="b551f-103">To ensure that your stored procedures perform correctly, you should edit existing procedures and remove those full-text related properties and settings that have been removed or deprecated.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b551f-104">Componente</span><span class="sxs-lookup"><span data-stu-id="b551f-104">Component</span></span>  
 <span data-ttu-id="b551f-105">Pesquisa de Texto Completo</span><span class="sxs-lookup"><span data-stu-id="b551f-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="b551f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b551f-106">Description</span></span>  
 <span data-ttu-id="b551f-107">As seguintes propriedades e configurações relacionadas à Pesquisa de Texto Completo foram removidas.</span><span class="sxs-lookup"><span data-stu-id="b551f-107">The following Full-Text Search-related properties and settings have been removed.</span></span>  
  
-   <span data-ttu-id="b551f-108">**DataTimeout**</span><span class="sxs-lookup"><span data-stu-id="b551f-108">**DataTimeout**</span></span>  
  
-   <span data-ttu-id="b551f-109">**ConnectTimeout**</span><span class="sxs-lookup"><span data-stu-id="b551f-109">**ConnectTimeout**</span></span>  
  
-   <span data-ttu-id="b551f-110">**Clean_up**</span><span class="sxs-lookup"><span data-stu-id="b551f-110">**Clean_up**</span></span>  
  
-   <span data-ttu-id="b551f-111">**LogSize**</span><span class="sxs-lookup"><span data-stu-id="b551f-111">**LogSize**</span></span>  
  
 <span data-ttu-id="b551f-112">As seguintes propriedades e configurações relacionadas à Pesquisa de Texto Completo foram removidas ou substituídas:</span><span class="sxs-lookup"><span data-stu-id="b551f-112">The following Full-Text Search-related properties and settings have been removed or deprecated:</span></span>  
  
-   <span data-ttu-id="b551f-113">'Path' do Catálogo de Texto Completo.</span><span class="sxs-lookup"><span data-stu-id="b551f-113">'Path' of the Full-Text Catalog.</span></span> <span data-ttu-id="b551f-114">O Catálogo de Texto Completo será um objeto lógico sem um caminho de arquivo específico no sistema.</span><span class="sxs-lookup"><span data-stu-id="b551f-114">The Full-Text Catalog will be a logic object without a specific file path in the system.</span></span>  
  
-   <span data-ttu-id="b551f-115">Habilitar ou desabilitar SP_FULLTEXT_DATABASE não tem mais efeito, uma vez que os bancos de dados estão sempre habilitados para Pesquisa de Texto Completo e por padrão no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b551f-115">Enable/disable in SP_FULLTEXT_DATABASE has no effect anymore as databases are enabled for Full-Text Search at all times and by default in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b551f-116">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="b551f-116">Corrective Action</span></span>  
 <span data-ttu-id="b551f-117">Modifique seus procedimentos armazenados para remover essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="b551f-117">Modify your stored procedures to remove these properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b551f-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b551f-118">See Also</span></span>  
 [<span data-ttu-id="b551f-119">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="b551f-119">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  

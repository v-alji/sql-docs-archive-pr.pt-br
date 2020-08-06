---
title: A atualização fará com que a pesquisa de texto completo use os separadores de palavras e os filtros em nível de instância, e não globais, por padrão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 93ee8fcb-d11c-49fa-8fac-51ed31a8f008
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b6cea7ab63351fad25f0205a614e364328171a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583987"
---
# <a name="upgrading-will-cause-full-text-search-to-use-instance-level-not-global-word-breakers-and-filters-by-default"></a><span data-ttu-id="4b7f2-102">Atualização fará com que a Pesquisa de Texto Completo use separadores de palavras e filtros em nível de instância, e não globais, por padrão</span><span class="sxs-lookup"><span data-stu-id="4b7f2-102">Upgrading will cause Full-Text Search to use instance-level, not global, word breakers and filters by default</span></span>
  <span data-ttu-id="4b7f2-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite os registro em nível de instância de novos separadores de palavras e filtros.</span><span class="sxs-lookup"><span data-stu-id="4b7f2-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a way to allow instance-level registration of new word breakers and filters.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4b7f2-104">Componente</span><span class="sxs-lookup"><span data-stu-id="4b7f2-104">Component</span></span>  
 <span data-ttu-id="4b7f2-105">Pesquisa de Texto Completo</span><span class="sxs-lookup"><span data-stu-id="4b7f2-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="4b7f2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="4b7f2-106">Description</span></span>  
 <span data-ttu-id="4b7f2-107">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite o registro de novos separadores de palavras e filtros em nível de instância.</span><span class="sxs-lookup"><span data-stu-id="4b7f2-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows the instance-level registration of new word breakers and filters.</span></span> <span data-ttu-id="4b7f2-108">Esse registro em nível de instância fornece isolamento funcional e de segurança entre instâncias.</span><span class="sxs-lookup"><span data-stu-id="4b7f2-108">This instance-level registration provides functional and security isolation between instances.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="4b7f2-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="4b7f2-109">Corrective Action</span></span>  
 <span data-ttu-id="4b7f2-110">Depois de atualizar para o `sp_fulltext_service` para definir a propriedade de serviço e `load_os_resources`, o que permitirá que os componentes sejam carregados.</span><span class="sxs-lookup"><span data-stu-id="4b7f2-110">After upgrading, use the `sp_fulltext_service` to set the service property and `load_os_resources`, which allows the components to be loaded.</span></span> <span data-ttu-id="4b7f2-111">Você deve executar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4b7f2-111">You must run the following:</span></span>  
  
 `sp_fulltext_service 'load_os_resources', 1`  
  
## <a name="see-also"></a><span data-ttu-id="4b7f2-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4b7f2-112">See Also</span></span>  
 [<span data-ttu-id="4b7f2-113">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="4b7f2-113">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  

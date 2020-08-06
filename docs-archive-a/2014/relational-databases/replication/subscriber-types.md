---
title: Tipos de assinante | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.subscribertypes.f1
ms.assetid: a70656cb-21c9-4489-be77-ccd396747e3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d356377dec1f5307fa136c94ea682c0824479a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582982"
---
# <a name="subscriber-types"></a><span data-ttu-id="85ebc-102">Tipos de Assinantes</span><span class="sxs-lookup"><span data-stu-id="85ebc-102">Subscriber Types</span></span>
  <span data-ttu-id="85ebc-103">A replicação de mesclagem permite especificar a que tipos de Assinantes uma publicação deve dar suporte.</span><span class="sxs-lookup"><span data-stu-id="85ebc-103">Merge replication allows you to specify the types of Subscribers that a publication must support.</span></span> <span data-ttu-id="85ebc-104">A seleção dos tipos de Assinantes define o *nível de compatibilidade da publicação*, que determina quais recursos podem ser usados por uma publicação.</span><span class="sxs-lookup"><span data-stu-id="85ebc-104">Selecting Subscriber types sets the *publication compatibility level*, which determines which features can be used by a publication.</span></span>  
  
 <span data-ttu-id="85ebc-105">Depois que um instantâneo de publicação é criado, o nível de compatibilidade da publicação pode ser aumentado (tornado mais restrito) na página **Geral** da caixa de diálogo **Propriedades de Publicação** ; o nível de compatibilidade não pode ser diminuído.</span><span class="sxs-lookup"><span data-stu-id="85ebc-105">After a publication snapshot is created, the publication compatibility level can be increased (made more restrictive) on the **General** page of the **Publication Properties** dialog box; the compatibility level cannot be decreased.</span></span>  
  
## <a name="options"></a><span data-ttu-id="85ebc-106">Opções</span><span class="sxs-lookup"><span data-stu-id="85ebc-106">Options</span></span>  
 <span data-ttu-id="85ebc-107">Selecione cada tipo de Assinante a que esta publicação deve dar suporte.</span><span class="sxs-lookup"><span data-stu-id="85ebc-107">Select each Subscriber type that this publication must support.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 <span data-ttu-id="85ebc-108">A publicação pode usar todos os recursos.</span><span class="sxs-lookup"><span data-stu-id="85ebc-108">The publication can use all features.</span></span>  
  
 [!INCLUDE[ssEW](../../includes/ssew-md.md)]  
 <span data-ttu-id="85ebc-109">A publicação exige que os arquivos de instantâneo estejam no formato de caractere (isto é tratado automaticamente pelo Agente de Instantâneo).</span><span class="sxs-lookup"><span data-stu-id="85ebc-109">The publication requires snapshot files to be in character format (this is handled automatically by the Snapshot Agent).</span></span> <span data-ttu-id="85ebc-110">O[!INCLUDE[ssEW](../../includes/ssew-md.md)] também tem várias restrições não relacionadas ao nível de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="85ebc-110">[!INCLUDE[ssEW](../../includes/ssew-md.md)] also has a number of restrictions not related to compatibility level.</span></span>  
  
 <span data-ttu-id="85ebc-111">Se essa opção for selecionada, a opção de sincronização da Web estará habilitada para a publicação.</span><span class="sxs-lookup"><span data-stu-id="85ebc-111">If this option is selected, the Web synchronization option is enabled for the publication.</span></span> <span data-ttu-id="85ebc-112">Para obter mais informações sobre a sincronização da Web, consulte [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="85ebc-112">For more information about Web synchronization, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ebc-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85ebc-113">See Also</span></span>  
 <span data-ttu-id="85ebc-114">[Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="85ebc-114">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="85ebc-115">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="85ebc-115">[Create a Publication](publish/create-a-publication.md) </span></span>  
 [<span data-ttu-id="85ebc-116">Exibir e modificar propriedades de Publicador e Distribuidor</span><span class="sxs-lookup"><span data-stu-id="85ebc-116">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  

---
title: Preparando procedimento armazenado (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6a613106-9f87-4caf-a23a-a726fc6561c5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9259352350a099db5d9b18411ad4da06dfb19819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583692"
---
# <a name="staging-stored-procedure-master-data-services"></a><span data-ttu-id="2897c-102">Preparando procedimento armazenado (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2897c-102">Staging Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="2897c-103">Ao iniciar o processo de preparo no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], você usa um entre três procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="2897c-103">When initiating the staging process from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you use one of three stored procedures.</span></span>  
  
-   <span data-ttu-id="2897c-104">stg.udp_name_Leaf</span><span class="sxs-lookup"><span data-stu-id="2897c-104">stg.udp_name_Leaf</span></span>  
  
-   <span data-ttu-id="2897c-105">stg.udp_name_Consolidated</span><span class="sxs-lookup"><span data-stu-id="2897c-105">stg.udp_name_Consolidated</span></span>  
  
-   <span data-ttu-id="2897c-106">stg.udp_name_Relationship</span><span class="sxs-lookup"><span data-stu-id="2897c-106">stg.udp_name_Relationship</span></span>  
  
 <span data-ttu-id="2897c-107">Onde nome é o nome da tabela de preparo que foi especificada quando a entidade foi criada.</span><span class="sxs-lookup"><span data-stu-id="2897c-107">Where name is the name of the staging table that was specified when the entity was created.</span></span>  
  
## <a name="staging-process-stored-procedure-parameters"></a><span data-ttu-id="2897c-108">Parâmetros do procedimento armazenado do processo de preparo</span><span class="sxs-lookup"><span data-stu-id="2897c-108">Staging Process Stored Procedure Parameters</span></span>  
 <span data-ttu-id="2897c-109">A tabela a seguir lista os parâmetros desses procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="2897c-109">The following table lists the parameters of these stored procedures.</span></span>  
  
|<span data-ttu-id="2897c-110">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="2897c-110">Parameter</span></span>|<span data-ttu-id="2897c-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="2897c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2897c-112">**VersionName**</span><span class="sxs-lookup"><span data-stu-id="2897c-112">**VersionName**</span></span><br /><br /> <span data-ttu-id="2897c-113">Necessária</span><span class="sxs-lookup"><span data-stu-id="2897c-113">Required</span></span>|<span data-ttu-id="2897c-114">O nome da versão.</span><span class="sxs-lookup"><span data-stu-id="2897c-114">The name of the version.</span></span> <span data-ttu-id="2897c-115">Pode ou não diferenciar maiúsculas de minúsculas, dependendo de sua configuração de ordenação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2897c-115">This may or may not be case-sensitive, depending on your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] collation setting.</span></span>|  
|<span data-ttu-id="2897c-116">**LogFlag**</span><span class="sxs-lookup"><span data-stu-id="2897c-116">**LogFlag**</span></span><br /><br /> <span data-ttu-id="2897c-117">Necessária</span><span class="sxs-lookup"><span data-stu-id="2897c-117">Required</span></span>|<span data-ttu-id="2897c-118">Determina se as transações são registradas em log durante o processo de preparo.</span><span class="sxs-lookup"><span data-stu-id="2897c-118">Determines whether transactions are logged during the staging process.</span></span> <span data-ttu-id="2897c-119">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="2897c-119">Possible values are:</span></span><br /><br /> <span data-ttu-id="2897c-120">**0**: não registrar transações em log.</span><span class="sxs-lookup"><span data-stu-id="2897c-120">**0**: Do not log transactions.</span></span><br /><span data-ttu-id="2897c-121">**1**: registrar transações em log.</span><span class="sxs-lookup"><span data-stu-id="2897c-121">**1**: Log transactions.</span></span><br /><br /> <br /><br /> <span data-ttu-id="2897c-122">Para obter mais informações sobre transações, consulte [Transações &#40;Master Data Services&#41;](transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2897c-122">For more information about transactions, see [Transactions &#40;Master Data Services&#41;](transactions-master-data-services.md).</span></span>|  
|<span data-ttu-id="2897c-123">**BatchTag**</span><span class="sxs-lookup"><span data-stu-id="2897c-123">**BatchTag**</span></span><br /><br /> <span data-ttu-id="2897c-124">Necessário, exceto pelo serviço Web</span><span class="sxs-lookup"><span data-stu-id="2897c-124">Required, except by web service</span></span>|<span data-ttu-id="2897c-125">O valor **BatchTag** conforme especificado na tabela de preparo.</span><span class="sxs-lookup"><span data-stu-id="2897c-125">The **BatchTag** value as specified in the staging table.</span></span>|  
|<span data-ttu-id="2897c-126">**Batch_ID**</span><span class="sxs-lookup"><span data-stu-id="2897c-126">**Batch_ID**</span></span><br /><br /> <span data-ttu-id="2897c-127">Necessário apenas pelo serviço Web</span><span class="sxs-lookup"><span data-stu-id="2897c-127">Required by web service only</span></span>|<span data-ttu-id="2897c-128">O valor **Batch_ID** , conforme especificado na tabela de preparo.</span><span class="sxs-lookup"><span data-stu-id="2897c-128">The **Batch_ID** value as specified in the staging table.</span></span>|  
  
### <a name="staging-process-stored-procedure-example"></a><span data-ttu-id="2897c-129">Exemplo de procedimento armazenado do processo de preparo</span><span class="sxs-lookup"><span data-stu-id="2897c-129">Staging Process Stored Procedure Example</span></span>  
 <span data-ttu-id="2897c-130">O exemplo a seguir mostra como iniciar o processo de preparo por meio do procedimento armazenado de preparo.</span><span class="sxs-lookup"><span data-stu-id="2897c-130">The following example shows how to start the staging process by using the staging stored procedure.</span></span>  
  
```  
USE [DATABASE_NAME]  
GO  
  
EXEC[stg].[udp_name_Leaf]  
      @VersionName = N'VERSION_1',  
@LogFlag = 1,  
@BatchTag = N'batch1'  
  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2897c-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2897c-131">See Also</span></span>  
 <span data-ttu-id="2897c-132">[Procedimento armazenado de validação &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2897c-132">[Validation Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="2897c-133">[Carregar ou atualizar Membros no Master Data Services usando o processo de preparo](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2897c-133">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 [<span data-ttu-id="2897c-134">Exibir erros que ocorrem durante o processo de preparo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2897c-134">View Errors that Occur During the Staging Process &#40;Master Data Services&#41;</span></span>](view-errors-that-occur-during-staging-master-data-services.md)  
  
  

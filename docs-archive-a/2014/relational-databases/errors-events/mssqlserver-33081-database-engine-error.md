---
title: MSSQLSERVER_33081 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33081 (Database Engine error)
ms.assetid: 839705e7-fa37-4c0d-9f3f-95a9eab98bcf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0752220cc20641d9b51a3a66fecc86f9efd63433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573063"
---
# <a name="mssqlserver_33081"></a><span data-ttu-id="f08b4-102">MSSQLSERVER_33081</span><span class="sxs-lookup"><span data-stu-id="f08b4-102">MSSQLSERVER_33081</span></span>
    
## <a name="details"></a><span data-ttu-id="f08b4-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f08b4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f08b4-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="f08b4-104">Product Name</span></span>|<span data-ttu-id="f08b4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f08b4-105">SQL Server</span></span>|  
|<span data-ttu-id="f08b4-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="f08b4-106">Event ID</span></span>|<span data-ttu-id="f08b4-107">33081</span><span class="sxs-lookup"><span data-stu-id="f08b4-107">33081</span></span>|  
|<span data-ttu-id="f08b4-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="f08b4-108">Event Source</span></span>|<span data-ttu-id="f08b4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f08b4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f08b4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f08b4-110">Component</span></span>|<span data-ttu-id="f08b4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f08b4-111">SQLEngine</span></span>|  
|<span data-ttu-id="f08b4-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="f08b4-112">Symbolic Name</span></span>|<span data-ttu-id="f08b4-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span><span class="sxs-lookup"><span data-stu-id="f08b4-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span></span>|  
|<span data-ttu-id="f08b4-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="f08b4-114">Message Text</span></span>|<span data-ttu-id="f08b4-115">Falha ao carregar o provedor criptográfico '%.\*ls' devido a uma assinatura inválida de Authenticode ou a um caminho de arquivo inválido.</span><span class="sxs-lookup"><span data-stu-id="f08b4-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span>  <span data-ttu-id="f08b4-116">Verifique as mensagens anteriores à procura de outras falhas.</span><span class="sxs-lookup"><span data-stu-id="f08b4-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f08b4-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="f08b4-117">Explanation</span></span>  
 <span data-ttu-id="f08b4-118">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde carregar o provedor criptográfico listado na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="f08b4-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to load the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="f08b4-119">Há várias falhas de API do Windows que poderiam causar esse erro.</span><span class="sxs-lookup"><span data-stu-id="f08b4-119">There are several Win API failures which might cause this error.</span></span> <span data-ttu-id="f08b4-120">O buffer de anéis contém o nome da API com falha e o código de erro do Windows retornado pela API.</span><span class="sxs-lookup"><span data-stu-id="f08b4-120">The ring buffer contains the name of the failed API and the Windows error code returned by the API.</span></span> <span data-ttu-id="f08b4-121">Para obter mais informações, consulte a exibição sys.dm_os_ring_buffers usando a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="f08b4-121">To get more information, query the sys.dm_os_ring_buffers view using the following query.</span></span>  
  
```  
SELECT * FROM sys.dm_os_ring_buffers   
WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
```  
  
## <a name="user-action"></a><span data-ttu-id="f08b4-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f08b4-122">User Action</span></span>  
 <span data-ttu-id="f08b4-123">Para investigar o problema, pesquise o código de erro do Windows no MSDN (https://msdn.microsoft.com/) ).</span><span class="sxs-lookup"><span data-stu-id="f08b4-123">To investigate the problem, search for the Windows error code in MSDN (https://msdn.microsoft.com/).</span></span> <span data-ttu-id="f08b4-124">Resolva o erro ou contate o [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f08b4-124">Resolve the error, or contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS for more information.</span></span> <span data-ttu-id="f08b4-125">Se for necessário contatar o CSS, colete as informações a seguir para nossa equipe de suporte.</span><span class="sxs-lookup"><span data-stu-id="f08b4-125">If you need to contact CSS, collect the following information for our support staff.</span></span>  
  
-   <span data-ttu-id="f08b4-126">O log de erros que mostra a erro de falha no carregamento do provedor criptográfico.</span><span class="sxs-lookup"><span data-stu-id="f08b4-126">The error log showing the failed to load cryptographic provider error.</span></span>  
  
-   <span data-ttu-id="f08b4-127">A saída da seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="f08b4-127">The output from the following statement:</span></span>  
  
    ```  
    SELECT * FROM sys.dm_os_ring_buffers   
    WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="f08b4-128">Tente coletar as informações do buffer de anéis imediatamente, pois as informações de buffer de anéis podem ser perdidas durante uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="f08b4-128">Try to collect the ring buffer information promptly as ring buffer information can be lost during a restart.</span></span>  
  
  

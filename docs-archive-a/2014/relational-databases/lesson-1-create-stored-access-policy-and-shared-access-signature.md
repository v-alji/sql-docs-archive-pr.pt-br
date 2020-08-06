---
title: Lição 2. Criar uma política no contêiner e gerar uma chave de assinatura de acesso compartilhado (SAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41674d9d-8132-4bff-be4d-85a861419f3d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab209f08d53b25a4791ef675e6fb6b78cab115f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684730"
---
# <a name="lesson-2-create-a-policy-on-container-and-generate-a-shared-access-signature-sas-key"></a><span data-ttu-id="ed963-103">Lição 2.</span><span class="sxs-lookup"><span data-stu-id="ed963-103">Lesson 2.</span></span> <span data-ttu-id="ed963-104">Criar uma política no contêiner e gerenciar uma chave SAS (assinatura de acesso compartilhado)</span><span class="sxs-lookup"><span data-stu-id="ed963-104">Create a policy on container and generate a Shared Access Signature (SAS) key</span></span>
  <span data-ttu-id="ed963-105">Nesta lição, você aprenderá a criar uma política no contêiner do Blob e também gerará uma chave de SAS.</span><span class="sxs-lookup"><span data-stu-id="ed963-105">In this lesson, you will learn how to create a policy on the Blob container and also generate a SAS key.</span></span>  
  
 <span data-ttu-id="ed963-106">Uma política de acesso armazenado fornece um nível de controle adicional sobre assinaturas de acesso compartilhado no lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="ed963-106">A stored access policy provides an additional level of control over shared access signatures on the server side.</span></span> <span data-ttu-id="ed963-107">Uma assinatura de acesso compartilhado é um URI que concede direitos de acesso restrito a contêineres, blobs, filas e tabelas.</span><span class="sxs-lookup"><span data-stu-id="ed963-107">A shared access signature is a URI that grants restricted access rights to containers, blobs, queues, and tables.</span></span> <span data-ttu-id="ed963-108">Ao usar esse novo aprimoramento, você precisa criar uma política em um contêiner com direitos de leitura, gravação e lista.</span><span class="sxs-lookup"><span data-stu-id="ed963-108">When using this new enhancement, you need to create a policy on a container with read, write, and list rights.</span></span>  
  
 <span data-ttu-id="ed963-109">Você pode criar uma política e uma assinatura de acesso compartilhado usando um destes métodos:</span><span class="sxs-lookup"><span data-stu-id="ed963-109">You can create a policy and a shared access signature by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="ed963-110">Operações da API REST do Azure: [criar contêiner](https://msdn.microsoft.com/library/azure/dd179468.aspx), [definir ACL de contêiner](https://msdn.microsoft.com/library/azure/dd179391.aspx)e [obter ACL de contêiner](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span><span class="sxs-lookup"><span data-stu-id="ed963-110">Azure REST API operations: [Create Container](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Set Container ACL](https://msdn.microsoft.com/library/azure/dd179391.aspx), and [Get Container ACL](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span></span>  
  
-   <span data-ttu-id="ed963-111">[Método CloudBlobContainer. GetSharedAccessSignature](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) no SDK do Azure.</span><span class="sxs-lookup"><span data-stu-id="ed963-111">[CloudBlobContainer.GetSharedAccessSignature Method](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) in the Azure SDK.</span></span>  
  
    ```  
  
       string signature = blob.GetSharedAccessSignature(new SharedAccessPolicy()   
        {   
            // Specify the expiration time for the signature.   
            SharedAccessExpiryTime = DateTime.Now.Years(1),   
            // Specify the permissions granted by the signature.    
            Permissions = SharedAccessPermissions.Write | SharedAccessPermissions.Read   
        });  
  
    ```  
  
-   <span data-ttu-id="ed963-112">Uma ferramenta de terceiros do Azure Explorer, como [Gerenciador de armazenamento do Azure](https://azurestorageexplorer.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="ed963-112">A third-party Azure explorer tool, such as [Azure Storage Explorer](https://azurestorageexplorer.codeplex.com/).</span></span>  
  
 <span data-ttu-id="ed963-113">**Próxima lição:**</span><span class="sxs-lookup"><span data-stu-id="ed963-113">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="ed963-114">Lição 3: Criar uma credencial do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed963-114">Lesson 3: Create a SQL Server Credential</span></span>](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)  
  

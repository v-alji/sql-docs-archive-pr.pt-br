---
title: Chave mestra de serviço | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server]
- service master key [SQL Server], about service master key
ms.assetid: 85f2095d-2590-4f59-8a29-7e100edd02bb
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: baeeffd49ac89ce85cf64932fbfd4982d7243887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686226"
---
# <a name="service-master-key"></a><span data-ttu-id="a0353-102">SMK (chave mestra de serviço)</span><span class="sxs-lookup"><span data-stu-id="a0353-102">Service Master Key</span></span>
  <span data-ttu-id="a0353-103">A chave mestra de serviço é a raiz da hierarquia de criptografia do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0353-103">The Service Master Key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="a0353-104">Ela é gerada automaticamente na primeira vez que é necessária para criptografar outra chave.</span><span class="sxs-lookup"><span data-stu-id="a0353-104">It is generated automatically the first time it is needed to encrypt another key.</span></span> <span data-ttu-id="a0353-105">Por padrão, a Chave Mestra do Serviço é criptografada com o uso da API de proteção aos dados do Windows e da chave da máquina local.</span><span class="sxs-lookup"><span data-stu-id="a0353-105">By default, the Service Master Key is encrypted using the Windows data protection API and using the local machine key.</span></span> <span data-ttu-id="a0353-106">A chave mestra de serviço só pode ser aberta pela conta de serviço do Windows na qual ela foi criada ou por uma entidade que tenha acesso ao nome e à senha da conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="a0353-106">The Service Master Key can only be opened by the Windows service account under which it was created or by a principal with access to both the service account name and its password.</span></span>  
  
 <span data-ttu-id="a0353-107">Gerar novamente ou restaurar a chave mestra de serviço envolve a descriptografia e uma nova criptografia da hierarquia de criptografia completa.</span><span class="sxs-lookup"><span data-stu-id="a0353-107">Regenerating or restoring the Service Master Key involves decrypting and re-encrypting the complete encryption hierarchy.</span></span> <span data-ttu-id="a0353-108">Essa operação de uso intensivo de recursos deve ser agendada durante um período de baixa demanda, a menos que a chave mestra esteja comprometida.</span><span class="sxs-lookup"><span data-stu-id="a0353-108">Unless the key has been compromised, this resource-intensive operation should be scheduled during a period of low demand.</span></span>  
  
 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] <span data-ttu-id="a0353-109">usa o algoritmo de criptografia AES para proteger a SMK (chave mestra de serviço) e a DMK (chave mestra de banco de dados).</span><span class="sxs-lookup"><span data-stu-id="a0353-109">uses the AES encryption algorithm to protect the service master key (SMK) and the database master key (DMK).</span></span> <span data-ttu-id="a0353-110">O AES é um algoritmo de criptografia mais novo que o 3DES usado em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="a0353-110">AES is a newer encryption algorithm than 3DES used in earlier versions.</span></span> <span data-ttu-id="a0353-111">Depois de atualizar uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] para [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , o SMK e o DMK devem ser regenerados para atualizar as chave mestras para AES.</span><span class="sxs-lookup"><span data-stu-id="a0353-111">After upgrading an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] the SMK and DMK should be regenerated in order to upgrade the master keys to AES.</span></span> <span data-ttu-id="a0353-112">Para obter mais informações sobre como regenerar a SMK, veja [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) e [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0353-112">For more information about regenerating the SMK, see [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) and [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="a0353-113">Melhor prática</span><span class="sxs-lookup"><span data-stu-id="a0353-113">Best Practice</span></span>  
 <span data-ttu-id="a0353-114">Faça backup da chave mestra de serviço e armazene a cópia com backup em um local externo, seguro.</span><span class="sxs-lookup"><span data-stu-id="a0353-114">Back up the Service Master Key and store the backed up copy in a secure, off-site location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a0353-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a0353-115">Related Tasks</span></span>  
 [<span data-ttu-id="a0353-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a0353-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-service-master-key-transact-sql)  
  
 [<span data-ttu-id="a0353-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a0353-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-service-master-key-transact-sql)  
  
 [<span data-ttu-id="a0353-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a0353-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-service-master-key-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="a0353-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0353-119">See Also</span></span>  
 [<span data-ttu-id="a0353-120">Hierarquia de criptografia</span><span class="sxs-lookup"><span data-stu-id="a0353-120">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  

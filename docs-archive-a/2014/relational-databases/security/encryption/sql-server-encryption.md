---
title: Criptografia do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], about encryption
- security [SQL Server], encryption
- cryptography [SQL Server], about cryptography
ms.assetid: ead0150e-4943-4ad5-84c8-36f85c7278f4
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 6fc68e6f3280a8e23d6a1bf4f364aadfffd69f85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686221"
---
# <a name="sql-server-encryption"></a><span data-ttu-id="e837b-102">Criptografia do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e837b-102">SQL Server Encryption</span></span>
  <span data-ttu-id="e837b-103">Criptografia é o processo de confundir dados pelo uso de uma chave ou senha.</span><span class="sxs-lookup"><span data-stu-id="e837b-103">Encryption is the process of obfuscating data by the use of a key or password.</span></span> <span data-ttu-id="e837b-104">Isso pode tornar os dados inúteis sem a chave de descriptrografia correspondente ou senha.</span><span class="sxs-lookup"><span data-stu-id="e837b-104">This can make the data useless without the corresponding decryption key or password.</span></span> <span data-ttu-id="e837b-105">A criptografia não resolve problemas de controle de acesso.</span><span class="sxs-lookup"><span data-stu-id="e837b-105">Encryption does not solve access control problems.</span></span> <span data-ttu-id="e837b-106">Porém, aumenta a segurança, limitando perda de dados mesmo se os controles de acesso forem ignorados.</span><span class="sxs-lookup"><span data-stu-id="e837b-106">However, it enhances security by limiting data loss even if access controls are bypassed.</span></span> <span data-ttu-id="e837b-107">Por exemplo, se o computador host do banco de dados for malconfigurado e um hacker obtiver dados confidenciais, as informações roubadas poderão ser inúteis se estiverem criptografadas.</span><span class="sxs-lookup"><span data-stu-id="e837b-107">For example, if the database host computer is misconfigured and a hacker obtains sensitive data, that stolen information might be useless if it is encrypted.</span></span>  
  
 <span data-ttu-id="e837b-108">Você pode usar criptografia no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para conexões, dados e procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="e837b-108">You can use encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for connections, data, and stored procedures.</span></span> <span data-ttu-id="e837b-109">A tabela seguinte contém mais informações sobre criptografia no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e837b-109">The following table contains more information about encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e837b-110">Embora a criptografia seja uma ferramenta valiosa para ajudar a garantir a segurança, não deve ser considerada em todos os dados ou conexões.</span><span class="sxs-lookup"><span data-stu-id="e837b-110">Although encryption is a valuable tool to help ensure security, it should not be considered for all data or connections.</span></span> <span data-ttu-id="e837b-111">Quando você estiver decidindo se a criptografia deve ser implementada, considere como os usuários acessarão os dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-111">When you are deciding whether to implement encryption, consider how users will access data.</span></span> <span data-ttu-id="e837b-112">Se os usuários acessarem dados por uma rede pública, a criptografia de dados poderá ser necessária para aumentar a segurança.</span><span class="sxs-lookup"><span data-stu-id="e837b-112">If users access data over a public network, data encryption might be required to increase security.</span></span> <span data-ttu-id="e837b-113">No entanto, se todos os acessos envolverem uma configuração de intranet segura, a criptografia poderá não ser necessária.</span><span class="sxs-lookup"><span data-stu-id="e837b-113">However, if all access involves a secure intranet configuration, encryption might not be required.</span></span> <span data-ttu-id="e837b-114">Qualquer uso de criptografia deve também incluir uma estratégia de manutenção de senhas, chaves e certificados.</span><span class="sxs-lookup"><span data-stu-id="e837b-114">Any use of encryption should also include a maintenance strategy for passwords, keys, and certificates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e837b-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e837b-115">In This Section</span></span>  
 [<span data-ttu-id="e837b-116">Hierarquia de criptografia</span><span class="sxs-lookup"><span data-stu-id="e837b-116">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
 <span data-ttu-id="e837b-117">Informações sobre a hierarquia de criptografia no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e837b-117">Information about the encryption hierarchy in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="e837b-118">Escolher um algoritmo de criptografia</span><span class="sxs-lookup"><span data-stu-id="e837b-118">Choose an Encryption Algorithm</span></span>](choose-an-encryption-algorithm.md)  
 <span data-ttu-id="e837b-119">Informações sobre como selecionar um algoritmo de criptografia eficaz.</span><span class="sxs-lookup"><span data-stu-id="e837b-119">Information about how to select an effective encrypting algorithm.</span></span>  
  
 [<span data-ttu-id="e837b-120">TDE &#40;Transparent Data Encryption&#41;</span><span class="sxs-lookup"><span data-stu-id="e837b-120">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)  
 <span data-ttu-id="e837b-121">Informações gerais sobre como criptografar dados de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="e837b-121">General information about how to encrypt data transparently.</span></span>  
  
 [<span data-ttu-id="e837b-122">Chaves de criptografia do SQL Server e banco de dados &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="e837b-122">SQL Server and Database Encryption Keys &#40;Database Engine&#41;</span></span>](sql-server-and-database-encryption-keys-database-engine.md)  
 <span data-ttu-id="e837b-123">No [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], as chaves de criptografia incluem uma combinação de chaves públicas, privadas e assimétricas, usadas para proteger dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="e837b-123">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], encryption keys include a combination of public, private, and symmetric keys that are used to protect sensitive data.</span></span> <span data-ttu-id="e837b-124">Esta seção explica como implementar e gerenciar chaves de criptografia.</span><span class="sxs-lookup"><span data-stu-id="e837b-124">This section explains how to implement and manage encryption keys.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="e837b-125">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="e837b-125">Related Content</span></span>  
 [<span data-ttu-id="e837b-126">Protegendo o SQL Server</span><span class="sxs-lookup"><span data-stu-id="e837b-126">Securing SQL Server</span></span>](../securing-sql-server.md)  
 <span data-ttu-id="e837b-127">Visão geral de como ajudar a proteger a plataforma do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e como trabalhar com usuários e objetos protegíveis.</span><span class="sxs-lookup"><span data-stu-id="e837b-127">Overview of how to help secure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] platform, and how to work with users and securable objects.</span></span>  
  
 [<span data-ttu-id="e837b-128">Funções criptográficas &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e837b-128">Cryptographic Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cryptographic-functions-transact-sql)  
 <span data-ttu-id="e837b-129">Informações sobre como implementar funções de criptografia.</span><span class="sxs-lookup"><span data-stu-id="e837b-129">Information about how to implement cryptographic functions.</span></span>  
  
 [<span data-ttu-id="e837b-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e837b-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbypassphrase-transact-sql)  
 <span data-ttu-id="e837b-131">Informações sobre como usar uma senha para criptografar dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-131">Information about how to use a password to encrypt data.</span></span>  
  
 [<span data-ttu-id="e837b-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e837b-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
 <span data-ttu-id="e837b-133">Informações sobre como usar uma chave simétrica para criptografar dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-133">Information about how to use a symmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="e837b-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e837b-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbyasymkey-transact-sql)  
 <span data-ttu-id="e837b-135">Informações sobre como usar uma chave assimétrica para criptografar dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-135">Information about how to use an asymmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="e837b-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e837b-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbycert-transact-sql)  
 <span data-ttu-id="e837b-137">Informações sobre como usar um certificado para criptografar dados.</span><span class="sxs-lookup"><span data-stu-id="e837b-137">Information about how to use a certificate to encrypt data.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="e837b-138">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="e837b-138">External Resources</span></span>  
 [<span data-ttu-id="e837b-139">10 etapas para SQL Server segurança 2005</span><span class="sxs-lookup"><span data-stu-id="e837b-139">10 Steps to SQL Server 2005 Security</span></span>](https://www.itprotoday.com/sql-server/10-steps-sql-server-2005-security)  
 <span data-ttu-id="e837b-140">Informações atuais sobre segurança do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e837b-140">Current information about [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e837b-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e837b-141">See Also</span></span>  
 <span data-ttu-id="e837b-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e837b-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span></span>  
 <span data-ttu-id="e837b-143">[Chaves de criptografia do SQL Server e banco de dados &#40;Mecanismo de Banco de Dados&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="e837b-143">[SQL Server and Database Encryption Keys &#40;Database Engine&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span></span>  
 [<span data-ttu-id="e837b-144">Fazer backup e restaurar as chave de criptografia do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e837b-144">Back Up and Restore Reporting Services Encryption Keys</span></span>](../../../reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)  
  
  

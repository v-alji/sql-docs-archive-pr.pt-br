---
title: Replicar dados em colunas criptografadas (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], replicating data
- encryption [SQL Server replication]
- publishing [SQL Server replication], encrypted columns
ms.assetid: d1f8f586-e5a3-4a71-9391-11198d42bfa3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e1528d81faa352fdcdf37abe9ad93fda190445c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680899"
---
# <a name="replicate-data-in-encrypted-columns-sql-server-management-studio"></a><span data-ttu-id="3249d-102">Replicar dados em colunas criptografadas (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3249d-102">Replicate Data in Encrypted Columns (SQL Server Management Studio)</span></span>
  <span data-ttu-id="3249d-103">A replicação permite que você publique dados criptografados em coluna.</span><span class="sxs-lookup"><span data-stu-id="3249d-103">Replication enables you to publish encrypted column data.</span></span> <span data-ttu-id="3249d-104">Para descriptografar e usar esses dados no Assinante, a chave usada para criptografar os dados no Publicador também deve estar presente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="3249d-104">To decrypt and use this data at the Subscriber, the key that was used to encrypt the data at the Publisher must also be present on the Subscriber.</span></span> <span data-ttu-id="3249d-105">A replicação não fornece um mecanismo seguro para transportar chaves de criptografia.</span><span class="sxs-lookup"><span data-stu-id="3249d-105">Replication does not provide a secure mechanism to transport encryption keys.</span></span> <span data-ttu-id="3249d-106">Você deve recriar a chave de criptografia manualmente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="3249d-106">You must manually re-create the encryption key at the Subscriber.</span></span> <span data-ttu-id="3249d-107">Este tópico mostra como criptografar uma coluna no Publicador e certificar-se de que a chave de criptografia está disponível no Assinante.</span><span class="sxs-lookup"><span data-stu-id="3249d-107">This topic shows you how to encrypt a column at the Publisher and make sure that the encryption key is available at the Subscriber.</span></span>  
  
 <span data-ttu-id="3249d-108">As etapas básicas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="3249d-108">The basic steps are as follows:</span></span>  
  
1.  <span data-ttu-id="3249d-109">Crie a chave simétrica no Publicador.</span><span class="sxs-lookup"><span data-stu-id="3249d-109">Create the symmetric key at the Publisher.</span></span>  
  
2.  <span data-ttu-id="3249d-110">Criptografe os dados da coluna com a chave simétrica.</span><span class="sxs-lookup"><span data-stu-id="3249d-110">Encrypt column data with the symmetric key.</span></span>  
  
3.  <span data-ttu-id="3249d-111">Publique a tabela com a coluna criptografada.</span><span class="sxs-lookup"><span data-stu-id="3249d-111">Publish the table with the encrypted column.</span></span>  
  
4.  <span data-ttu-id="3249d-112">Assine a publicação.</span><span class="sxs-lookup"><span data-stu-id="3249d-112">Subscribe to the publication.</span></span>  
  
5.  <span data-ttu-id="3249d-113">Inicialize a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3249d-113">Initialize the subscription.</span></span>  
  
6.  <span data-ttu-id="3249d-114">Recrie a chave simétrica no Assinante usando os mesmos valores para ALGORITMO, KEY_SOURCE e IDENTITY_VALUE como na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3249d-114">Recreate the symmetric key at the Subscriber using same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span>  
  
7.  <span data-ttu-id="3249d-115">Acesse os dados de coluna criptografados.</span><span class="sxs-lookup"><span data-stu-id="3249d-115">Access the encrypted column data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3249d-116">Você deve usar uma chave simétrica para criptografar dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="3249d-116">You should use a symmetric key to encrypt column data.</span></span> <span data-ttu-id="3249d-117">A própria chave simétrica pode ser protegida através de meios diferentes no Publicador e no Assinante.</span><span class="sxs-lookup"><span data-stu-id="3249d-117">The symmetric key itself can be secured by different means at the Publisher and Subscriber.</span></span>  
  
### <a name="to-create-and-replicate-encrypted-column-data"></a><span data-ttu-id="3249d-118">Para criar e reproduzir dados em coluna criptografada</span><span class="sxs-lookup"><span data-stu-id="3249d-118">To create and replicate encrypted column data</span></span>  
  
1.  <span data-ttu-id="3249d-119">No Publicador, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3249d-119">At the Publisher, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3249d-120">O valor de KEY_SOURCE é um dado valioso que pode ser usado recriar a chave simétrica e descriptografar os dados.</span><span class="sxs-lookup"><span data-stu-id="3249d-120">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="3249d-121">KEY_SOURCE sempre deve ser armazenado e transportado de modo seguro.</span><span class="sxs-lookup"><span data-stu-id="3249d-121">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
2.  <span data-ttu-id="3249d-122">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) para abrir a chave nova.</span><span class="sxs-lookup"><span data-stu-id="3249d-122">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
3.  <span data-ttu-id="3249d-123">Use a função [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) para criptografar dados de coluna no Publicador.</span><span class="sxs-lookup"><span data-stu-id="3249d-123">Use the [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) function to encrypt column data at the Publisher.</span></span>  
  
4.  <span data-ttu-id="3249d-124">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) para fechar a chave.</span><span class="sxs-lookup"><span data-stu-id="3249d-124">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
5.  <span data-ttu-id="3249d-125">Publique a tabela que contém a coluna criptografada.</span><span class="sxs-lookup"><span data-stu-id="3249d-125">Publish the table that contains the encrypted column.</span></span> <span data-ttu-id="3249d-126">Para obter mais informações, consulte [Criar uma assinatura](../publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="3249d-126">For more information, see [Create a Publication](../publish/create-a-publication.md).</span></span>  
  
6.  <span data-ttu-id="3249d-127">Assine a publicação.</span><span class="sxs-lookup"><span data-stu-id="3249d-127">Subscribe to the publication.</span></span> <span data-ttu-id="3249d-128">Para obter mais informações, consulte [Criar uma assinatura pull](../create-a-pull-subscription.md) ou [Criar uma assinatura push](../create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3249d-128">For more information, see [Create a Pull Subscription](../create-a-pull-subscription.md) or [Create a Push Subscription](../create-a-push-subscription.md).</span></span>  
  
7.  <span data-ttu-id="3249d-129">Inicialize a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3249d-129">Initialize the subscription.</span></span> <span data-ttu-id="3249d-130">Para obter mais informações, consulte [Criar e aplicar o instantâneo inicial](../create-and-apply-the-initial-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="3249d-130">For more information, see [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span></span>  
  
8.  <span data-ttu-id="3249d-131">No Assinante, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) usando os mesmos valores para ALGORITHM, KEY_SOURCE, e IDENTITY_VALUE da etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3249d-131">At the Subscriber, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span> <span data-ttu-id="3249d-132">Você pode especificar um valor diferente para ENCRYPTION BY.</span><span class="sxs-lookup"><span data-stu-id="3249d-132">You can specify a different value for ENCRYPTION BY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3249d-133">O valor de KEY_SOURCE é um dado valioso que pode ser usado recriar a chave simétrica e descriptografar os dados.</span><span class="sxs-lookup"><span data-stu-id="3249d-133">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="3249d-134">KEY_SOURCE sempre deve ser armazenado e transportado de modo seguro.</span><span class="sxs-lookup"><span data-stu-id="3249d-134">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
9. <span data-ttu-id="3249d-135">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) para abrir a chave nova.</span><span class="sxs-lookup"><span data-stu-id="3249d-135">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
10. <span data-ttu-id="3249d-136">Use a função [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) para descriptografar dados replicados no Assinante.</span><span class="sxs-lookup"><span data-stu-id="3249d-136">Use the [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) function to decrypt replicated data at the Subscriber.</span></span>  
  
11. <span data-ttu-id="3249d-137">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) para fechar a chave.</span><span class="sxs-lookup"><span data-stu-id="3249d-137">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3249d-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3249d-138">Example</span></span>  
 <span data-ttu-id="3249d-139">Este exemplo cria uma chave simétrica, um certificado que é usado para auxiliar a proteger a chave simétrica e uma chave mestra.</span><span class="sxs-lookup"><span data-stu-id="3249d-139">This example creates a symmetric key, a certificate that is used to help secure the symmetric key, and a master key.</span></span> <span data-ttu-id="3249d-140">Essas chaves são criadas no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="3249d-140">These keys are created in the publication database.</span></span> <span data-ttu-id="3249d-141">Depois elas são usadas para criar uma coluna criptografada (EncryptedCreditCardApprovalCode) na tabela `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="3249d-141">They are then used to create an encrypted column (EncryptedCreditCardApprovalCode) in the `SalesOrderHeader` table.</span></span> <span data-ttu-id="3249d-142">Essa coluna é publicada na publicação AdvWorksSalesOrdersMerge em vez da coluna não criptografada CreditCardApprovalCode.</span><span class="sxs-lookup"><span data-stu-id="3249d-142">This column is published in the AdvWorksSalesOrdersMerge publication instead of the unencrypted CreditCardApprovalCode column.</span></span> <span data-ttu-id="3249d-143">Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="3249d-143">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="3249d-144">Se for necessário armazenar credenciais em um arquivo de script, você deverá proteger o arquivo para impedir acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="3249d-144">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_PublishEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/publishencryptedcolumn.sql#sp_publishencryptedcolumn)]  
  
 [!code-sql[HowTo#sp_AddMergeArticle](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepub.sql#sp_addmergearticle)]  
  
## <a name="example"></a><span data-ttu-id="3249d-145">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3249d-145">Example</span></span>  
 <span data-ttu-id="3249d-146">Este exemplo recria a mesma chave simétrica no banco de dados de assinatura usando os mesmos valores para ALGORITHM, KEY_SOURCE, e IDENTITY_VALUE do primeiro exemplo.</span><span class="sxs-lookup"><span data-stu-id="3249d-146">This example recreates the same symmetric key in the subscription database using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE from the first example.</span></span> <span data-ttu-id="3249d-147">Este exemplo supõe que você já inicializou uma assinatura à publicação AdvWorksSalesOrdersMerge para replicar a coluna criptografada.</span><span class="sxs-lookup"><span data-stu-id="3249d-147">This example assumes that you have already initialized a subscription to the AdvWorksSalesOrdersMerge publication to replicate the encrypted column.</span></span> <span data-ttu-id="3249d-148">Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="3249d-148">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="3249d-149">Se for necessário armazenar credenciais em um arquivo de script, deve-se proteger o arquivo durante o armazenamento e o transporte para evitar o acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="3249d-149">If you must store credentials in a script file, you must secure the file during storage and transport to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_SubscriberEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/subscriberencryptedcolumn.sql#sp_subscriberencryptedcolumn)]  
  
## <a name="see-also"></a><span data-ttu-id="3249d-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3249d-150">See Also</span></span>  
 <span data-ttu-id="3249d-151">[Segurança de Replicação do SQL Server](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3249d-151">[SQL Server Replication Security](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="3249d-152">Criar chaves simétricas idênticas em dois servidores</span><span class="sxs-lookup"><span data-stu-id="3249d-152">Create Identical Symmetric Keys on Two Servers</span></span>](../../security/encryption/create-identical-symmetric-keys-on-two-servers.md)  
  
  

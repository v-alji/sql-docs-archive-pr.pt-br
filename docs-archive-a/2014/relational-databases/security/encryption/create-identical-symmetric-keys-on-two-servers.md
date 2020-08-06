---
title: Criar chaves simétricas idênticas em dois servidores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- symmetric keys [SQL Server], creating
ms.assetid: a13d0b21-a43b-43c0-9c22-7ba8f3d15e80
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 38eaccffff89b0be7e59f628fcfb9b6e772a02b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685505"
---
# <a name="create-identical-symmetric-keys-on-two-servers"></a><span data-ttu-id="32a60-102">Criar chaves simétricas idênticas em dois servidores</span><span class="sxs-lookup"><span data-stu-id="32a60-102">Create Identical Symmetric Keys on Two Servers</span></span>
  <span data-ttu-id="32a60-103">Este tópico descreve como criar chaves simétricas idênticas em dois servidores diferentes no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32a60-103">This topic describes how to create identical symmetric keys on two different servers in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="32a60-104">Para descriptografar texto cifrado, você precisa da chave que foi usada para criptografá-lo.</span><span class="sxs-lookup"><span data-stu-id="32a60-104">In order to decrypt ciphertext, you need the key that was used to encrypt it.</span></span> <span data-ttu-id="32a60-105">Quando ocorrem criptografia e descriptografia em um único banco de dados, a chave é armazenada no banco de dados e fica disponível, dependendo das permissões, tanto para criptografia quanto para descriptografia.</span><span class="sxs-lookup"><span data-stu-id="32a60-105">When both encryption and decryption occur in a single database, the key is stored in the database and it is available, depending on permissions, for both encryption and decryption.</span></span> <span data-ttu-id="32a60-106">Mas quando a criptografia e a descriptografia ocorrem em bancos de dados ou servidores separados, a chave armazenada em um banco de dados não estará disponível para uso no segundo banco de dados</span><span class="sxs-lookup"><span data-stu-id="32a60-106">But when encryption and decryption occur in separate databases or on separate servers, the key stored in one database is not available for use on the second database</span></span>  
  
 <span data-ttu-id="32a60-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="32a60-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="32a60-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="32a60-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="32a60-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="32a60-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="32a60-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="32a60-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="32a60-111">Para criar chaves simétricas idênticas em dois servidores diferentes, usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="32a60-111">To create identical symmetric keys on two different servers, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="32a60-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="32a60-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="32a60-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="32a60-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="32a60-114">Quando uma chave simétrica é criada, a chave simétrica deve ser criptografada usando pelo menos um dos seguintes: senha, certificado, chave simétrica, chave assimétrica ou provedor.</span><span class="sxs-lookup"><span data-stu-id="32a60-114">When a symmetric key is created, the symmetric key must be encrypted by using at least one of the following: certificate, password, symmetric key, asymmetric key, or PROVIDER.</span></span> <span data-ttu-id="32a60-115">A chave pode ter mais de uma criptografia de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="32a60-115">The key can have more than one encryption of each type.</span></span> <span data-ttu-id="32a60-116">Em outras palavras, uma única chave simétrica pode ser criptografada com o uso de vários certificados, senhas, chaves simétricas e chaves assimétricas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="32a60-116">In other words, a single symmetric key can be encrypted by using multiple certificates, passwords, symmetric keys, and asymmetric keys at the same time.</span></span>  
  
-   <span data-ttu-id="32a60-117">Quando uma chave simétrica é criptografada com uma senha e não com a chave pública da chave mestre do banco de dados, o algoritmo de criptografia TRIPLE DES é usado.</span><span class="sxs-lookup"><span data-stu-id="32a60-117">When a symmetric key is encrypted with a password instead of the public key of the database master key, the TRIPLE DES encryption algorithm is used.</span></span> <span data-ttu-id="32a60-118">Por esse motivo, as chaves criadas com um algoritmo de criptografia forte, como AES, são protegidas por um algoritmo mais fraco.</span><span class="sxs-lookup"><span data-stu-id="32a60-118">Because of this, keys that are created with a strong encryption algorithm, such as AES, are themselves secured by a weaker algorithm.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="32a60-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="32a60-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="32a60-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="32a60-120">Permissions</span></span>  
 <span data-ttu-id="32a60-121">Requer permissão ALTER ANY SYMMETRIC KEY no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="32a60-121">Requires ALTER ANY SYMMETRIC KEY permission on the database.</span></span> <span data-ttu-id="32a60-122">Se AUTHORIZATION for especificada, será necessária a permissão IMPERSONATE no usuário de banco de dados ou a permissão ALTER na função de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="32a60-122">If AUTHORIZATION is specified, requires IMPERSONATE permission on the database user or ALTER permission on the application role.</span></span> <span data-ttu-id="32a60-123">Se a criptografia for por certificado ou chave assimétrica, exigirá a permissão VIEW DEFINITION no certificado ou na chave assimétrica.</span><span class="sxs-lookup"><span data-stu-id="32a60-123">If encryption is by certificate or asymmetric key, requires VIEW DEFINITION permission on the certificate or asymmetric key.</span></span> <span data-ttu-id="32a60-124">Somente logons do Windows, logons do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e funções de aplicativo podem ter chaves simétricas.</span><span class="sxs-lookup"><span data-stu-id="32a60-124">Only Windows logins, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins, and application roles can own symmetric keys.</span></span> <span data-ttu-id="32a60-125">Grupos e funções não podem possuir chaves simétricas.</span><span class="sxs-lookup"><span data-stu-id="32a60-125">Groups and roles cannot own symmetric keys.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="32a60-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="32a60-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-identical-symmetric-keys-on-two-different-servers"></a><span data-ttu-id="32a60-127">Para criar chaves simétricas idênticas em dois servidores diferentes</span><span class="sxs-lookup"><span data-stu-id="32a60-127">To create identical symmetric keys on two different servers</span></span>  
  
1.  <span data-ttu-id="32a60-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32a60-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="32a60-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="32a60-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="32a60-130">Crie a chave executando as instruções CREATE MASTER KEY, CREATE CERTIFICATE e CREATE SYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="32a60-130">Create a key by running the following CREATE MASTER KEY, CREATE CERTIFICATE, and CREATE SYMMETRIC KEY statements.</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'My p@55w0Rd';  
    GO  
    CREATE CERTIFICATE [cert_keyProtection] WITH SUBJECT = 'Key Protection';  
    GO  
    CREATE SYMMETRIC KEY [key_DataShare] WITH  
        KEY_SOURCE = 'My key generation bits. This is a shared secret!',  
        ALGORITHM = AES_256,   
        IDENTITY_VALUE = 'Key Identity generation bits. Also a shared secret'  
        ENCRYPTION BY CERTIFICATE [cert_keyProtection];  
    GO  
    ```  
  
4.  <span data-ttu-id="32a60-131">Conecte a uma instância de servidor separada, abra uma Janela de Consulta diferente e execute as instruções SQL acima para criar a mesma chave no segundo servidor.</span><span class="sxs-lookup"><span data-stu-id="32a60-131">Connect to a separate server instance, open a different Query Window, and run the SQL statements above to create the same key on the second server.</span></span>  
  
5.  <span data-ttu-id="32a60-132">Teste as chaves executando primeiro a instrução OPEN e a instrução SELECT abaixo no primeiro servidor.</span><span class="sxs-lookup"><span data-stu-id="32a60-132">Test the keys by first running the OPEN SYMMETRIC KEY statement and the SELECT statement below on the first server.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    SELECT encryptbykey(key_guid('key_DataShare'), 'MyData' )  
    GO  
    -- For example, the output might look like this: 0x2152F8DA8A500A9EDC2FAE26D15C302DA70D25563DAE7D5D1102E3056CE9EF95CA3E7289F7F4D0523ED0376B155FE9C3  
    ```  
  
6.  <span data-ttu-id="32a60-133">No segundo servidor, cole o resultado da instrução SELECT anterior no seguinte código como o valor de `@blob` e execute esse código para verificar se a chave duplicada pode descriptografar o texto cifrado.</span><span class="sxs-lookup"><span data-stu-id="32a60-133">On the second server, paste the result of the previous SELECT statement into the following code as the value of `@blob` and run the following code to verify that the duplicate key can decrypt the ciphertext.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    DECLARE @blob varbinary(8000);  
    SET @blob = SELECT CONVERT(varchar(8000), decryptbykey(@blob));  
    GO  
    ```  
  
7.  <span data-ttu-id="32a60-134">Feche a chave simétrica em ambos os servidores.</span><span class="sxs-lookup"><span data-stu-id="32a60-134">Close the symmetric key on both servers.</span></span>  
  
    ```  
    CLOSE SYMMETRIC KEY [key_DataShare];  
    GO  
    ```  
  
 <span data-ttu-id="32a60-135">Para saber mais, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="32a60-135">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="32a60-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32a60-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="32a60-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32a60-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="32a60-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32a60-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)  
  
-   [<span data-ttu-id="32a60-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32a60-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
  
-   [<span data-ttu-id="32a60-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32a60-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/decryptbykey-transact-sql)  
  
-   [<span data-ttu-id="32a60-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32a60-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/open-symmetric-key-transact-sql)  
  
  

---
title: Fazer backup de uma chave mestra de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], exporting
ms.assetid: 7ad9a0a0-6e4f-4f7b-8801-8c1b9d49c4d8
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 9a66d28fea8289719d3efb2351409e0f14379ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685509"
---
# <a name="back-up-a-database-master-key"></a><span data-ttu-id="38549-102">Fazer backup da chave mestra de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="38549-102">Back Up a Database Master Key</span></span>
  <span data-ttu-id="38549-103">Este tópico descreve como fazer o backup de uma chave mestra de banco de dados no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38549-103">This topic describes how to back up a database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="38549-104">A chave mestra de banco de dados é usada para criptografar outras chaves e certificados dentro de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="38549-104">The database master key is used to encrypt other keys and certificates inside a database.</span></span> <span data-ttu-id="38549-105">Se ela for excluída ou estiver corrompida, é possível que o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não consiga descriptografar essas chaves e os dados criptografados com elas poderão ser efetivamente perdidos.</span><span class="sxs-lookup"><span data-stu-id="38549-105">If it is deleted or corrupted, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may be unable to decrypt those keys, and the data encrypted using them will be effectively lost.</span></span> <span data-ttu-id="38549-106">Por esta razão, faça backup da chave mestra de banco de dados e armazene o backup em um local externo seguro.</span><span class="sxs-lookup"><span data-stu-id="38549-106">For this reason, you should back up the database master key and store the backup in a secure off-site location.</span></span>  
  
 <span data-ttu-id="38549-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="38549-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="38549-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="38549-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="38549-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="38549-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="38549-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="38549-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="38549-111">Para fazer o backup de uma chave mestra de banco de dados usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38549-111">To back up a database master key using Transact-SQL</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="38549-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="38549-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="38549-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="38549-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="38549-114">A chave mestra deve estar aberta e, portanto, descriptografada antes de ser feito o back up.</span><span class="sxs-lookup"><span data-stu-id="38549-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="38549-115">Se for criptografada com a chave mestra de serviço, a chave mestra não terá que ser aberta explicitamente.</span><span class="sxs-lookup"><span data-stu-id="38549-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened.</span></span> <span data-ttu-id="38549-116">No entanto, se a chave mestra só for criptografada com uma senha, ela deve ser aberta explicitamente.</span><span class="sxs-lookup"><span data-stu-id="38549-116">But if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="38549-117">Recomendamos que você faça o backup da chave mestra assim que ela for criada e armazene o backup em um local externo seguro.</span><span class="sxs-lookup"><span data-stu-id="38549-117">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="38549-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="38549-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="38549-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="38549-119">Permissions</span></span>  
 <span data-ttu-id="38549-120">Exige a permissão CONTROL no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="38549-120">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="Procedure"></a><span data-ttu-id="38549-121">Usando SQL Server Management Studio com Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38549-121">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-database-master-key"></a><span data-ttu-id="38549-122">Fazer backup da chave mestra de banco de dados</span><span class="sxs-lookup"><span data-stu-id="38549-122">To back-up the database master key</span></span>  
  
1.  <span data-ttu-id="38549-123">No [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], conecte à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que contém a chave mestra do banco de dados da qual você deseja fazer backup.</span><span class="sxs-lookup"><span data-stu-id="38549-123">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the database master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="38549-124">Escolha uma senha que será usada para criptografar a chave mestra de banco de dados na mídia de backup.</span><span class="sxs-lookup"><span data-stu-id="38549-124">Choose a password that will be used to encrypt the database master key on the backup medium.</span></span> <span data-ttu-id="38549-125">Esta senha está sujeita à verificação de complexidade.</span><span class="sxs-lookup"><span data-stu-id="38549-125">This password is subject to complexity checks.</span></span>  
  
3.  <span data-ttu-id="38549-126">Obtenha uma mídia de backup removível para armazenar uma cópia da chave de backup.</span><span class="sxs-lookup"><span data-stu-id="38549-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="38549-127">Identifique um diretório NTFS no qual criar o backup da chave.</span><span class="sxs-lookup"><span data-stu-id="38549-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="38549-128">É aí que você criará o arquivo especificado na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="38549-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="38549-129">O diretório deve ser protegido com ACLs (listas de controle de acesso) altamente restritivas.</span><span class="sxs-lookup"><span data-stu-id="38549-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="38549-130">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38549-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="38549-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="38549-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="38549-132">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="38549-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key. Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;   
    GO  
    OPEN MASTER KEY DECRYPTION BY PASSWORD = 'sfj5300osdVdgwdfkli7';   
  
    BACKUP MASTER KEY TO FILE = 'c:\temp\exportedmasterkey'   
        ENCRYPTION BY PASSWORD = 'sd092735kjn$&adsg';   
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="38549-133">O caminho do arquivo para a chave e a senha da chave (se existir) serão diferentes do que é indicado acima.</span><span class="sxs-lookup"><span data-stu-id="38549-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="38549-134">Certifique-se de que ambos sejam específicos da sua configuração de servidor e chave.</span><span class="sxs-lookup"><span data-stu-id="38549-134">Please make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="38549-135">Copie o arquivo na mídia de backup e verifique a cópia.</span><span class="sxs-lookup"><span data-stu-id="38549-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="38549-136">Armazene o backup em um local seguro, fora do site.</span><span class="sxs-lookup"><span data-stu-id="38549-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="38549-137">Para obter mais informações, veja [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) e [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="38549-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  

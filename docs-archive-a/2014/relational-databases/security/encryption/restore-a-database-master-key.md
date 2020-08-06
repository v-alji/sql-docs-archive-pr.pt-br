---
title: Restaurar uma chave mestra de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], importing
ms.assetid: 16897cc5-db8f-43bb-a38e-6855c82647cf
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 614ba8bdc494ae7e7e5b3ed7b62390721ef642a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686228"
---
# <a name="restore-a-database-master-key"></a><span data-ttu-id="f2bb1-102">Restaurar uma chave mestra de banco de dados</span><span class="sxs-lookup"><span data-stu-id="f2bb1-102">Restore a Database Master Key</span></span>
  <span data-ttu-id="f2bb1-103">Este tópico descreve como restaurar a chave mestra de banco de dados no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2bb1-103">This topic describes how to restore the database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f2bb1-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f2bb1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f2bb1-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="f2bb1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f2bb1-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f2bb1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f2bb1-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="f2bb1-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="f2bb1-108">Para restaurar a chave mestra de banco de dados usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2bb1-108">To restore the database master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f2bb1-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f2bb1-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f2bb1-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f2bb1-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f2bb1-111">Quando a chave mestra é restaurada, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] descriptografa todas as chaves atualmente criptografadas com a chave mestra ativa e criptografa essas chaves com a chave mestra restaurada.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-111">When the master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys that are encrypted with the currently active master key, and then encrypts these keys with the restored master key.</span></span> <span data-ttu-id="f2bb1-112">Essa operação de uso intensivo de recursos deve ser agendada em um período de baixa demanda.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-112">This resource-intensive operation should be scheduled during a period of low demand.</span></span> <span data-ttu-id="f2bb1-113">Se a chave mestra de banco de dados atual não for aberta ou não puder ser aberta, ou se qualquer chave criptografada com ela não puder ser descriptografada, a operação de restauração falhará.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-113">If the current database master key is not open or cannot be opened, or if any of the keys that are encrypted by it cannot be decrypted, the restore operation fails.</span></span>  
  
-   <span data-ttu-id="f2bb1-114">Se qualquer uma dessas descriptografias falhar, a restauração falhará.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-114">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="f2bb1-115">É possível usar a opção FORCE para ignorar erros, mas essa opção causará a perda dos dados que não puderem ser descriptografados.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-115">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="f2bb1-116">Se a chave mestra foi criptografada pela chave mestra de serviço, a chave mestra restaurada também será criptografada pela chave mestra de serviço.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-116">If the master key was encrypted by the service master key, the restored master key will also be encrypted by the service master key.</span></span>  
  
-   <span data-ttu-id="f2bb1-117">Se não houver nenhuma chave mestra no banco de dados atual, RESTORE MASTER KEY criará uma chave mestra.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-117">If there is no master key in the current database, RESTORE MASTER KEY creates a master key.</span></span> <span data-ttu-id="f2bb1-118">A nova chave mestra não será criptografada automaticamente com a chave mestra de serviço.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-118">The new master key will not be automatically encrypted with the service master key.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f2bb1-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="f2bb1-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f2bb1-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="f2bb1-120">Permissions</span></span>  
 <span data-ttu-id="f2bb1-121">Exige a permissão CONTROL no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-121">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="SSMSProcedure"></a><span data-ttu-id="f2bb1-122">Usando SQL Server Management Studio com Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2bb1-122">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-restore-the-database-master-key"></a><span data-ttu-id="f2bb1-123">Para restaurar a chave mestra de banco de dados</span><span class="sxs-lookup"><span data-stu-id="f2bb1-123">To restore the database master key</span></span>  
  
1.  <span data-ttu-id="f2bb1-124">Recupere uma cópia do backup da chave mestra de banco de dados de uma mídia de backup física ou de um diretório no sistema de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-124">Retrieve a copy of the backed-up database master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="f2bb1-125">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2bb1-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="f2bb1-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-126">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="f2bb1-127">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the database master key of the AdventureWorks2012 database.  
    USE AdventureWorks2012;  
    GO  
    RESTORE MASTER KEY   
        FROM FILE = 'c:\backups\keys\AdventureWorks2012_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003#GHkf02597gheij04'   
        ENCRYPTION BY PASSWORD = '259087M#MyjkFkjhywiyedfgGDFD';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2bb1-128">O caminho do arquivo para a chave e a senha da chave (se existir) serão diferentes do que é indicado acima.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-128">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="f2bb1-129">Certifique-se de que ambos sejam específicos da sua configuração de servidor e chave.</span><span class="sxs-lookup"><span data-stu-id="f2bb1-129">Please make sure that both are specific to your server and key set-up.</span></span>  
  
 <span data-ttu-id="f2bb1-130">Para obter mais informações, consulte [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="f2bb1-130">For more information, see [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span></span>  
  
  

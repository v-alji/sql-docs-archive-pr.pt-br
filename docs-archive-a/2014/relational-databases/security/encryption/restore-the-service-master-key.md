---
title: Restaurar a chave mestra de serviço | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], importing
- service master key [SQL Server], restoring
ms.assetid: 14bdbbbe-d384-4692-b670-4243d2466fe1
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 2ad99fc9baa518d50678ddd6e6db1ec554658823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686229"
---
# <a name="restore-the-service-master-key"></a><span data-ttu-id="e2b50-102">Restaurar a chave mestra de serviço</span><span class="sxs-lookup"><span data-stu-id="e2b50-102">Restore the Service Master Key</span></span>
  <span data-ttu-id="e2b50-103">Este tópico descreve como restaurar a chave mestra de serviço no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2b50-103">This topic describes how to restore the service master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e2b50-104">É improvável que você alguma vez precise restaurar essa chave.</span><span class="sxs-lookup"><span data-stu-id="e2b50-104">It is unlikely that you will ever need to restore the service master key.</span></span> <span data-ttu-id="e2b50-105">Se precisar, você deverá continuar com precaução extrema.</span><span class="sxs-lookup"><span data-stu-id="e2b50-105">If you do, you should proceed with extreme caution.</span></span> <span data-ttu-id="e2b50-106">Para obter mais informações, consulte [Back Up the Service Master Key](service-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="e2b50-106">For more information, see [Back Up the Service Master Key](service-master-key.md).</span></span>  
  
 <span data-ttu-id="e2b50-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="e2b50-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e2b50-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="e2b50-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e2b50-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="e2b50-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e2b50-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="e2b50-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="e2b50-111">Para restaurar a chave mestra de serviço usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2b50-111">To restore the service master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e2b50-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e2b50-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e2b50-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="e2b50-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e2b50-114">Quando a chave mestra de serviço é restaurada, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] descriptografa todas as chaves e segredos que foram criptografados com a chave mestra de serviço atual e, em seguida, criptografa a chave mestra de serviço carregada do arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="e2b50-114">When the service master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys and secrets that have been encrypted with the current service master key, and then encrypts them with the service master key loaded from the backup file.</span></span>  
  
-   <span data-ttu-id="e2b50-115">Se qualquer uma dessas descriptografias falhar, a restauração falhará.</span><span class="sxs-lookup"><span data-stu-id="e2b50-115">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="e2b50-116">É possível usar a opção FORCE para ignorar erros, mas essa opção causará a perda dos dados que não puderem ser descriptografados.</span><span class="sxs-lookup"><span data-stu-id="e2b50-116">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="e2b50-117">A nova geração da hierarquia de criptografia é uma operação que utiliza muitos recursos.</span><span class="sxs-lookup"><span data-stu-id="e2b50-117">Regenerating the encryption hierarchy is a resource-intensive operation.</span></span> <span data-ttu-id="e2b50-118">É recomendável agendá-la em um período de baixa demanda.</span><span class="sxs-lookup"><span data-stu-id="e2b50-118">You should schedule this during a period of low demand.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e2b50-119">A chave mestra de serviço é a raiz da hierarquia de criptografia do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2b50-119">The service master key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="e2b50-120">A chave mestra de serviço protege todas as outras chaves diretamente ou indiretamente na árvore.</span><span class="sxs-lookup"><span data-stu-id="e2b50-120">The service master key directly or indirectly secures all other keys in the tree.</span></span> <span data-ttu-id="e2b50-121">Se uma chave dependente não puder ser descriptografada durante uma restauração forçada, os dados protegidos por ela serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="e2b50-121">If a dependent key cannot be decrypted during a forced restore, data that is secured by that key will be lost.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e2b50-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="e2b50-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e2b50-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="e2b50-123">Permissions</span></span>  
 <span data-ttu-id="e2b50-124">Exige a permissão CONTROL SERVER no servidor.</span><span class="sxs-lookup"><span data-stu-id="e2b50-124">Requires CONTROL SERVER permission on the server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e2b50-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2b50-125">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-the-service-master-key"></a><span data-ttu-id="e2b50-126">Para restaurar a chave mestra de serviço</span><span class="sxs-lookup"><span data-stu-id="e2b50-126">To restore the service master key</span></span>  
  
1.  <span data-ttu-id="e2b50-127">Recupere uma cópia do backup da chave mestra de serviço de uma mídia de backup física ou de um diretório no sistema de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="e2b50-127">Retrieve a copy of the backed-up service master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="e2b50-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2b50-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="e2b50-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e2b50-129">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="e2b50-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e2b50-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the service master key from a backup file.  
    RESTORE SERVICE MASTER KEY   
        FROM FILE = 'c:\temp_backups\keys\service_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2b50-131">O caminho do arquivo para a chave e a senha da chave (se existir) serão diferentes do que é indicado acima.</span><span class="sxs-lookup"><span data-stu-id="e2b50-131">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="e2b50-132">Certifique-se de que ambos sejam específicos da sua configuração de servidor e chave.</span><span class="sxs-lookup"><span data-stu-id="e2b50-132">Please make sure that both are specific to your server and key set-up.</span></span>  
  
  

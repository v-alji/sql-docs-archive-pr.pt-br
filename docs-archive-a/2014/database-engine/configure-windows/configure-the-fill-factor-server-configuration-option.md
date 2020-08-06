---
title: Configurar a opção de configuração de servidor fill factor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fill factor option [SQL Server]
ms.assetid: b920ec34-ba8b-4bb8-af53-a3ffd06bafa6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02258c92b4a09277d371e605fd4729ba9fda3461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574907"
---
# <a name="configure-the-fill-factor-server-configuration-option"></a><span data-ttu-id="277be-102">Configurar a opção fill factor de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="277be-102">Configure the fill factor Server Configuration Option</span></span>
  <span data-ttu-id="277be-103">Este tópico descreve como configurar a opção de configuração de servidor **fill factor** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="277be-103">This topic describes how to configure the **fill factor** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="277be-104">O fator de preenchimento é fornecido para ajustar o armazenamento e o desempenho de dados de índice.</span><span class="sxs-lookup"><span data-stu-id="277be-104">Fill factor is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="277be-105">Quando um índice é criado ou recriado, o valor de fator de preenchimento determina a porcentagem de espaço em cada página de nível folha a ser preenchida com dados, reservando o restante como espaço livre para futuro crescimento.</span><span class="sxs-lookup"><span data-stu-id="277be-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the rest as free space for future growth.</span></span> <span data-ttu-id="277be-106">Para obter mais informações, veja [Especificar fator de preenchimento para um índice](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="277be-106">For more information, see [Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span></span>  
  
 <span data-ttu-id="277be-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="277be-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="277be-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="277be-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="277be-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="277be-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="277be-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="277be-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="277be-111">**Para configurar a opção fill factor, usando:**</span><span class="sxs-lookup"><span data-stu-id="277be-111">**To configure the fill factor option, using:**</span></span>  
  
     [<span data-ttu-id="277be-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="277be-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="277be-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="277be-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="277be-114">**Acompanhamento:**  [depois de configurar a opção fill factor option](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="277be-114">**Follow Up:**  [After you configure the fill factor option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="277be-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="277be-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="277be-116">Recomendações</span><span class="sxs-lookup"><span data-stu-id="277be-116">Recommendations</span></span>  
  
-   <span data-ttu-id="277be-117">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="277be-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="277be-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="277be-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="277be-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="277be-119">Permissions</span></span>  
 <span data-ttu-id="277be-120">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="277be-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="277be-121">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="277be-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="277be-122">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="277be-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="277be-123">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="277be-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="277be-124">Para configurar a opção fill factor</span><span class="sxs-lookup"><span data-stu-id="277be-124">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="277be-125">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="277be-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="277be-126">Clique no nó **Configurações de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="277be-126">Click the **Database Settings** node.</span></span>  
  
3.  <span data-ttu-id="277be-127">Na caixa **Fator de preenchimento padrão do índice** , digite ou selecione o fator de preenchimento do índice desejado.</span><span class="sxs-lookup"><span data-stu-id="277be-127">In the **Default index fill factor** box, type or select the index fill factor that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="277be-128">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="277be-128">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="277be-129">Para configurar a opção fill factor</span><span class="sxs-lookup"><span data-stu-id="277be-129">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="277be-130">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="277be-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="277be-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="277be-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="277be-132">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="277be-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="277be-133">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `fill factor` como `100`.</span><span class="sxs-lookup"><span data-stu-id="277be-133">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `fill factor` option to `100`.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="277be-134">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="277be-134">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-fill-factor-option"></a><a name="FollowUp"></a> <span data-ttu-id="277be-135">Acompanhamento: depois de configurar a opção fill factor option</span><span class="sxs-lookup"><span data-stu-id="277be-135">Follow Up: After you configure the fill factor option</span></span>  
 <span data-ttu-id="277be-136">O servidor deve ser reiniciado para que a configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="277be-136">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277be-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="277be-137">See Also</span></span>  
 <span data-ttu-id="277be-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="277be-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="277be-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="277be-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="277be-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="277be-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="277be-141">[Especificar o fator de preenchimento para um índice](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="277be-141">[Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span></span>  
 <span data-ttu-id="277be-142">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="277be-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="277be-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="277be-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="277be-144">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="277be-144">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  

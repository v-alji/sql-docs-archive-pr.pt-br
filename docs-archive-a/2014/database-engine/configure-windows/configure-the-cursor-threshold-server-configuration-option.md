---
title: Configurar a opção de configuração de servidor cursor threshold | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cursor threshold option
ms.assetid: 189f2067-c6c4-48bd-9bd9-65f6b2021c12
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0d7fd9ecafda270a02f1fba9f5dd74adc9e299d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583836"
---
# <a name="configure-the-cursor-threshold-server-configuration-option"></a><span data-ttu-id="8af77-102">Configurar a opção de configuração de servidor cursor threshold</span><span class="sxs-lookup"><span data-stu-id="8af77-102">Configure the cursor threshold Server Configuration Option</span></span>
  <span data-ttu-id="8af77-103">Este tópico descreve como configurar a opção de configuração de servidor **cursor threshold** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8af77-103">This topic describes how to configure the **cursor threshold** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8af77-104">A opção **cursor threshold** especifica o número de linhas no conjunto de cursores em que os conjuntos de chaves de cursor são gerados de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="8af77-104">The **cursor threshold** option specifies the number of rows in the cursor set at which cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="8af77-105">Quando os cursores geram um conjunto de chaves para um conjunto de resultados, o otimizador de consulta calcula o número de linhas que serão retornadas para aquele conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="8af77-105">When cursors generate a keyset for a result set, the query optimizer estimates the number of rows that will be returned for that result set.</span></span> <span data-ttu-id="8af77-106">Se o otimizador de consulta calcular que o número de linhas retornadas é maior do que esse limite, o cursor será gerado de forma assíncrona, permitindo que o usuário busque linhas do cursor enquanto o cursor continua sendo populado.</span><span class="sxs-lookup"><span data-stu-id="8af77-106">If the query optimizer estimates that the number of returned rows is greater than this threshold, the cursor is generated asynchronously, allowing the user to fetch rows from the cursor while the cursor continues to be populated.</span></span> <span data-ttu-id="8af77-107">Caso contrário, o cursor é gerado de forma síncrona e a consulta aguarda até que todas as linhas sejam retornadas.</span><span class="sxs-lookup"><span data-stu-id="8af77-107">Otherwise, the cursor is generated synchronously, and the query waits until all rows are returned.</span></span>  
  
 <span data-ttu-id="8af77-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8af77-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8af77-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8af77-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8af77-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8af77-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8af77-111">Recomendações</span><span class="sxs-lookup"><span data-stu-id="8af77-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="8af77-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="8af77-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8af77-113">**Para configurar a opção cursor threshold usando:**</span><span class="sxs-lookup"><span data-stu-id="8af77-113">**To configure the cursor threshold option, using:**</span></span>  
  
     [<span data-ttu-id="8af77-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8af77-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8af77-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8af77-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="8af77-116">**Acompanhamento:**  [depois de configurar a opção cursor threshold](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="8af77-116">**Follow Up:**  [After you configure the cursor threshold option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8af77-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8af77-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8af77-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8af77-118">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8af77-119">não dá suporte à geração de cursores [!INCLUDE[tsql](../../includes/tsql-md.md)] controlados por conjunto de chaves ou estáticos de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="8af77-119">does not support generating keyset-driven or static [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors asynchronously.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="8af77-120">, como OPEN ou FETCH, são em lote, de modo que não é preciso gerar cursores [!INCLUDE[tsql](../../includes/tsql-md.md)] assincronamente.</span><span class="sxs-lookup"><span data-stu-id="8af77-120">cursor operations such as OPEN or FETCH are batched, so there is no need for the asynchronous generation of [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8af77-121">continua a dar suporte a cursores de servidor de API (interface de programação de aplicativo) estáticos ou controlados por conjunto de chaves assíncronos nos quais OPEN de baixa latência é uma preocupação devido às viagens de ida e volta do cliente para cada operação de cursor.</span><span class="sxs-lookup"><span data-stu-id="8af77-121">continues to support asynchronous keyset-driven or static application programming interface (API) server cursors where low latency OPEN is a concern, due to client round trips for each cursor operation.</span></span>  
  
-   <span data-ttu-id="8af77-122">A exatidão do otimizador de consulta para determinar uma estimativa do número de linhas em um conjunto de chaves depende da moeda das estatísticas para cada tabela no cursor.</span><span class="sxs-lookup"><span data-stu-id="8af77-122">The accuracy of the query optimizer to determine an estimate for the number of rows in a keyset depends on the currency of the statistics for each of the tables in the cursor.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="8af77-123">Recomendações</span><span class="sxs-lookup"><span data-stu-id="8af77-123">Recommendations</span></span>  
  
-   <span data-ttu-id="8af77-124">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8af77-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="8af77-125">Se você definir o **cursor threshold** como -1, todos os conjuntos de chaves serão gerados de forma síncrona, o que beneficiará pequenos conjuntos de cursores.</span><span class="sxs-lookup"><span data-stu-id="8af77-125">If you set **cursor threshold** to -1, all keysets are generated synchronously, which benefits small cursor sets.</span></span> <span data-ttu-id="8af77-126">Se você definir o **cursor threshold** como 0, todos os conjuntos de chaves serão gerados de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="8af77-126">If you set **cursor threshold** to 0, all cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="8af77-127">Com outros valores, o otimizador de consulta irá comparar o número de linhas previstas no cursor definido e criará o conjunto de chaves de forma assíncrona se ele exceder o número definido em **cursor threshold**.</span><span class="sxs-lookup"><span data-stu-id="8af77-127">With other values, the query optimizer compares the number of expected rows in the cursor set and builds the keyset asynchronously if it exceeds the number set in **cursor threshold**.</span></span> <span data-ttu-id="8af77-128">Não defina **cursor threshold** com um valor muito baixo, pois conjuntos de resultados pequenos são criados melhor de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="8af77-128">Do not set **cursor threshold** too low, because small result sets are better built synchronously.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8af77-129">Segurança</span><span class="sxs-lookup"><span data-stu-id="8af77-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8af77-130">Permissões</span><span class="sxs-lookup"><span data-stu-id="8af77-130">Permissions</span></span>  
 <span data-ttu-id="8af77-131">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="8af77-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="8af77-132">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="8af77-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="8af77-133">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="8af77-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8af77-134">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8af77-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="8af77-135">Para configurar a opção cursor threshold</span><span class="sxs-lookup"><span data-stu-id="8af77-135">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="8af77-136">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8af77-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8af77-137">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="8af77-137">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="8af77-138">Em **Diversos**, altere a opção **Limite do Cursor** para o valor desejado.</span><span class="sxs-lookup"><span data-stu-id="8af77-138">Under **Miscellaneous**, change the **Cursor Threshold** option to the value you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8af77-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8af77-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="8af77-140">Para configurar a opção cursor threshold</span><span class="sxs-lookup"><span data-stu-id="8af77-140">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="8af77-141">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8af77-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8af77-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8af77-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8af77-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8af77-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8af77-144">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir a opção `cursor threshold` como `0` para que os conjuntos de chaves dos cursores sejam gerados de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="8af77-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the `cursor threshold` option to `0` so that cursor keysets are generated asynchronously.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cursor threshold', 0 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="8af77-145">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8af77-145">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cursor-threshold-option"></a><a name="FollowUp"></a> <span data-ttu-id="8af77-146">Acompanhamento: depois de configurar a opção cursor threshold</span><span class="sxs-lookup"><span data-stu-id="8af77-146">Follow Up: After you configure the cursor threshold option</span></span>  
 <span data-ttu-id="8af77-147">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="8af77-147">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af77-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8af77-148">See Also</span></span>  
 <span data-ttu-id="8af77-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8af77-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span></span>  
 <span data-ttu-id="8af77-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8af77-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="8af77-151">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8af77-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="8af77-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8af77-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="8af77-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8af77-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  

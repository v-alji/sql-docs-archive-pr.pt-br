---
title: Configurar a opção de configuração de servidor default full-text language | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- languages [full-text search]
- default full-text language option
ms.assetid: 0fa8785b-0830-4a52-aff5-fcf8268b72fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ec0736326a4da0708d125bfc480996d54bb86c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569649"
---
# <a name="configure-the-default-full-text-language-server-configuration-option"></a><span data-ttu-id="50e5b-102">Configurar opção de configuração de servidor default full-text language</span><span class="sxs-lookup"><span data-stu-id="50e5b-102">Configure the default full-text language Server Configuration Option</span></span>
  <span data-ttu-id="50e5b-103">Este tópico descreve como configurar a `default full-text language` opção de configuração de servidor no usando o ou o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="50e5b-103">This topic describes how to configure the `default full-text language` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="50e5b-104">A `default full-text language` opção especifica um valor de idioma padrão para índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="50e5b-104">The `default full-text language` option specifies a default language value for full-text indexes.</span></span> <span data-ttu-id="50e5b-105">A análise linguística é realizada em todos os dados que se encontram indexados com texto completo e depende do idioma dos dados.</span><span class="sxs-lookup"><span data-stu-id="50e5b-105">Linguistic analysis is performed on all data that is full-text indexed and is dependent on the language of the data.</span></span> <span data-ttu-id="50e5b-106">O valor padrão dessa opção é o idioma do servidor.</span><span class="sxs-lookup"><span data-stu-id="50e5b-106">The default value of this option is the language of the server.</span></span> <span data-ttu-id="50e5b-107">Para uma versão localizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a instalação define a `default full-text language` opção para o idioma do servidor se houver uma correspondência apropriada.</span><span class="sxs-lookup"><span data-stu-id="50e5b-107">For a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup sets the `default full-text language` option to the language of the server if an appropriate match exists.</span></span> <span data-ttu-id="50e5b-108">Para uma versão não localizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a opção `default full-text language` fica em inglês.</span><span class="sxs-lookup"><span data-stu-id="50e5b-108">For a non-localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the `default full-text language` option is English.</span></span>  
  
 <span data-ttu-id="50e5b-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="50e5b-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="50e5b-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="50e5b-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="50e5b-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="50e5b-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="50e5b-112">Recomendações</span><span class="sxs-lookup"><span data-stu-id="50e5b-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="50e5b-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="50e5b-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="50e5b-114">**Para configurar a opção default full-text language usando:**</span><span class="sxs-lookup"><span data-stu-id="50e5b-114">**To configure the default full-text language option, using:**</span></span>  
  
     [<span data-ttu-id="50e5b-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50e5b-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="50e5b-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50e5b-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="50e5b-117">**Acompanhamento:**  [depois de configurar a opção default full-text language](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="50e5b-117">**Follow Up:**  [After you configure the default full-text language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="50e5b-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="50e5b-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="50e5b-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="50e5b-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="50e5b-120">O valor da `default full-text language` opção é usado em um índice de texto completo quando nenhum idioma é especificado para uma coluna por meio da opção language **language_term** nas instruções CREATE FULLTEXT INDEX ou ALTER FULLTEXT index.</span><span class="sxs-lookup"><span data-stu-id="50e5b-120">The value of the `default full-text language` option is used in a full-text index when no language is specified for a column through the LANGUAGE **language_term** option in the CREATE FULLTEXT INDEX or ALTER FULLTEXT INDEX statements.</span></span> <span data-ttu-id="50e5b-121">Se o idioma de texto completo padrão não tiver suporte ou se o pacote de análise linguística não estiver disponível, a operação CREATE ou ALTER irá falhar e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retornará uma mensagem de erro informando que o idioma especificado não é válido.</span><span class="sxs-lookup"><span data-stu-id="50e5b-121">If the default full-text language is not supported or the linguistic analysis package is not available, the CREATE or ALTER operation will fail and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will return an error message stating that the language specified is not valid.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="50e5b-122">Recomendações</span><span class="sxs-lookup"><span data-stu-id="50e5b-122">Recommendations</span></span>  
  
-   <span data-ttu-id="50e5b-123">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="50e5b-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="50e5b-124">A `default full-text language` opção requer um valor LCID.</span><span class="sxs-lookup"><span data-stu-id="50e5b-124">The `default full-text language` option requires an LCID value.</span></span> <span data-ttu-id="50e5b-125">Para ver uma lista de LCIDs com suporte e seus idiomas relacionados, consulte [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50e5b-125">For a list of supported LCIDs and their related languages, see [sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).</span></span> <span data-ttu-id="50e5b-126">Outros idiomas também podem estar disponíveis; por exemplo, via fornecedores de software independentes.</span><span class="sxs-lookup"><span data-stu-id="50e5b-126">Other languages may also be available from independent software vendors, for example.</span></span> <span data-ttu-id="50e5b-127">Se nenhum dialeto de idioma específico for encontrado, o serviço Mecanismo de Pesquisa de Texto Completo alternará para o idioma principal automaticamente.</span><span class="sxs-lookup"><span data-stu-id="50e5b-127">If no specific language dialect is found, the Full-Text Engine will automatically switch to the primary language.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="50e5b-128">Segurança</span><span class="sxs-lookup"><span data-stu-id="50e5b-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="50e5b-129">Permissões</span><span class="sxs-lookup"><span data-stu-id="50e5b-129">Permissions</span></span>  
 <span data-ttu-id="50e5b-130">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="50e5b-130">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="50e5b-131">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="50e5b-131">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="50e5b-132">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="50e5b-132">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="50e5b-133">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50e5b-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="50e5b-134">Para configurar a opção default full-text language</span><span class="sxs-lookup"><span data-stu-id="50e5b-134">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="50e5b-135">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="50e5b-135">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="50e5b-136">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="50e5b-136">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="50e5b-137">Em Diversos, use **Idioma de Texto Completo Padrão** para especificar um valor de idioma padrão para colunas indexadas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="50e5b-137">Under Miscellaneous, use **Default Full Text Language** to specify a default language value for full-text indexed columns.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="50e5b-138">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50e5b-138">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-full-text-language-option"></a><span data-ttu-id="50e5b-139">Para configurar a opção default full-text language</span><span class="sxs-lookup"><span data-stu-id="50e5b-139">To configure the default full-text language option</span></span>  
  
1.  <span data-ttu-id="50e5b-140">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50e5b-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="50e5b-141">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="50e5b-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="50e5b-142">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="50e5b-142">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="50e5b-143">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `default full-text` como Holandês (`1043`).</span><span class="sxs-lookup"><span data-stu-id="50e5b-143">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `default full-text` option to Dutch (`1043`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'default full-text language', 1043 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="50e5b-144">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="50e5b-144">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-full-text-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="50e5b-145">Acompanhamento: depois de configurar a opção default full-text language</span><span class="sxs-lookup"><span data-stu-id="50e5b-145">Follow Up: After you configure the default full-text language option</span></span>  
 <span data-ttu-id="50e5b-146">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="50e5b-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e5b-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50e5b-147">See Also</span></span>  
 <span data-ttu-id="50e5b-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50e5b-148">[sys.fulltext_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) </span></span>  
 <span data-ttu-id="50e5b-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50e5b-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="50e5b-150">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="50e5b-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="50e5b-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50e5b-151">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="50e5b-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50e5b-152">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="50e5b-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50e5b-153">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  

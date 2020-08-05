---
title: Configurar a opção de configuração de servidor two digit year cutoff | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- two digit year cutoff option
- four-digit years [SQL Server]
ms.assetid: d94e81b6-f2e6-47ef-b497-ec3d827a1646
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c31c1d87c8b743132dd90d495f73ef711dc1f813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572169"
---
# <a name="configure-the-two-digit-year-cutoff-server-configuration-option"></a><span data-ttu-id="0ac78-102">Configurar a opção two digit year cutoff de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="0ac78-102">Configure the two digit year cutoff Server Configuration Option</span></span>
  <span data-ttu-id="0ac78-103">Este tópico descreve como configurar a opção de configuração de servidor **two digit year cutoff** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ac78-103">This topic describes how to configure the **two digit year cutoff** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0ac78-104">A opção **two digit year cutoff** especifica um número inteiro de 1753 até 9999 que representa o ano de corte para interpretar anos com dois dígitos como anos com quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="0ac78-104">The **two digit year cutoff** option specifies an integer from 1753 to 9999 that represents the cutoff year for interpreting two-digit years as four-digit years.</span></span> <span data-ttu-id="0ac78-105">O tempo padrão abrangido para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é 1950-2049, que representa um ano de corte de 2049.</span><span class="sxs-lookup"><span data-stu-id="0ac78-105">The default time span for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 1950-2049, which represents a cutoff year of 2049.</span></span> <span data-ttu-id="0ac78-106">Isso significa que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interpreta um ano de dois dígitos de 49 como 2049, um ano de dois dígitos 50 como 1950 e um ano de dois dígitos 99 como 1999.</span><span class="sxs-lookup"><span data-stu-id="0ac78-106">This means that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interprets a two-digit year of 49 as 2049, a two-digit year of 50 as 1950, and a two-digit year of 99 as 1999.</span></span> <span data-ttu-id="0ac78-107">Para manter a compatibilidade com versões anteriores, deixe a configuração no valor padrão.</span><span class="sxs-lookup"><span data-stu-id="0ac78-107">To maintain backward compatibility, leave the setting at the default value.</span></span>  
  
 <span data-ttu-id="0ac78-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="0ac78-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0ac78-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0ac78-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0ac78-110">Recomendações</span><span class="sxs-lookup"><span data-stu-id="0ac78-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="0ac78-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="0ac78-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0ac78-112">**Para configurar a opção two-digit year cutoff, usando:**</span><span class="sxs-lookup"><span data-stu-id="0ac78-112">**To configure the two digit year cutoff option, using:**</span></span>  
  
     [<span data-ttu-id="0ac78-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0ac78-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0ac78-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0ac78-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="0ac78-115">**Acompanhamento:**  [após configurar a opção two-digit year cutoff](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="0ac78-115">**Follow Up:**  [After you configure the two digit year cutoff option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0ac78-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0ac78-116">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="0ac78-117">Recomendações</span><span class="sxs-lookup"><span data-stu-id="0ac78-117">Recommendations</span></span>  
  
-   <span data-ttu-id="0ac78-118">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ac78-118">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="0ac78-119">Objetos de automação OLE usam 2030 como o ano de corte de dois dígitos.</span><span class="sxs-lookup"><span data-stu-id="0ac78-119">OLE Automation objects use 2030 as the two-digit cutoff year.</span></span> <span data-ttu-id="0ac78-120">Você pode usar a opção **two digit year cutoff** para proporcionar consistência em valores de data entre o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="0ac78-120">You can use the **two digit year cutoff** option to provide consistency in date values between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and client applications.</span></span> <span data-ttu-id="0ac78-121">Porém, para evitar ambiguidade de datas, use anos de quatro dígitos em seus dados.</span><span class="sxs-lookup"><span data-stu-id="0ac78-121">However, to avoid ambiguity with dates, use four-digit years in your data.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0ac78-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="0ac78-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0ac78-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="0ac78-123">Permissions</span></span>  
 <span data-ttu-id="0ac78-124">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="0ac78-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="0ac78-125">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="0ac78-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="0ac78-126">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="0ac78-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0ac78-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0ac78-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="0ac78-128">Para configurar a opção two-digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="0ac78-128">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="0ac78-129">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0ac78-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="0ac78-130">Clique no nó **Configuração de servidores diversos** .</span><span class="sxs-lookup"><span data-stu-id="0ac78-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="0ac78-131">Em **Suporte a ano de dois dígitos**, na caixa **Quando um ano de dois dígitos é inserido**, **interprete como um ano intermediário** , digite ou selecione um valor que é o ano final do tempo abrangido.</span><span class="sxs-lookup"><span data-stu-id="0ac78-131">Under **Two digit year support**, in the **When a two digit year is entered**, **interpret it as a year between** box, type or select a value that is the ending year of the time span.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0ac78-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0ac78-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="0ac78-133">Para configurar a opção two-digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="0ac78-133">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="0ac78-134">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ac78-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0ac78-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="0ac78-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0ac78-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0ac78-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0ac78-137">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `two digit year cutoff` como `2030`.</span><span class="sxs-lookup"><span data-stu-id="0ac78-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `two digit year cutoff` option to `2030`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'two digit year cutoff', 2030 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="0ac78-138">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0ac78-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-two-digit-year-cutoff-option"></a><a name="FollowUp"></a> <span data-ttu-id="0ac78-139">Acompanhamento: após configurar a opção two-digit year cutoff</span><span class="sxs-lookup"><span data-stu-id="0ac78-139">Follow Up: After you configure the two digit year cutoff option</span></span>  
 <span data-ttu-id="0ac78-140">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="0ac78-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac78-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ac78-141">See Also</span></span>  
 <span data-ttu-id="0ac78-142">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ac78-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="0ac78-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ac78-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="0ac78-144">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ac78-144">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  

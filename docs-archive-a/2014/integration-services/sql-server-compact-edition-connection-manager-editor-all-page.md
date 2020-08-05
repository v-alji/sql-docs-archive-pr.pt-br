---
title: Editor do Gerenciador de conexões do SQL Server Compact Edition (página todas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlmobileconnection.all.f1
helpviewer_keywords:
- SQL Server Compact Connection Manager Editor
ms.assetid: f9fbff4b-c502-44b3-8e7b-398d66e82206
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f881d63de5435426475c3aed4b666870d706b40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572594"
---
# <a name="sql-server-compact-edition-connection-manager-editor-all-page"></a><span data-ttu-id="8013f-102">Editor do Gerenciador de Conexões do SQL Server Compact Edition (Página Tudo)</span><span class="sxs-lookup"><span data-stu-id="8013f-102">SQL Server Compact Edition Connection Manager Editor (All Page)</span></span>
  <span data-ttu-id="8013f-103">Use a caixa de diálogo **Gerenciador de Conexões do SQL Server Compact Edition** para especificar as propriedades de conexão com um banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="8013f-103">Use the **SQL Server Compact Edition Connection Manager** dialog box to specify properties for connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="8013f-104">Para saber mais sobre o Gerenciador de conexões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition, consulte [Gerenciador de conexões do SQL Server Compact Edition](connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8013f-104">To learn more about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition connection manager, see [SQL Server Compact Edition Connection Manager](connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8013f-105">Opções</span><span class="sxs-lookup"><span data-stu-id="8013f-105">Options</span></span>  
 <span data-ttu-id="8013f-106">**Limite de AutoShrink**</span><span class="sxs-lookup"><span data-stu-id="8013f-106">**AutoShrink Threshold**</span></span>  
 <span data-ttu-id="8013f-107">Especifique a quantidade de espaço livre, em percentual, que será permitido no banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact antes que o processo de redução automática seja executado.</span><span class="sxs-lookup"><span data-stu-id="8013f-107">Specify the amount of free space, as a percentage, that is allowed in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database before the autoshrink process runs.</span></span>  
  
 <span data-ttu-id="8013f-108">**Escalonamento de Bloqueio Padrão**</span><span class="sxs-lookup"><span data-stu-id="8013f-108">**Default Lock Escalation**</span></span>  
 <span data-ttu-id="8013f-109">Especifique o número de bloqueios de banco de dados que o banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact adquire antes de tentar escalonar bloqueios.</span><span class="sxs-lookup"><span data-stu-id="8013f-109">Specify the number of database locks that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database acquires before it tries to escalate locks.</span></span>  
  
 <span data-ttu-id="8013f-110">**Tempos Limite de Bloqueio Padrão**</span><span class="sxs-lookup"><span data-stu-id="8013f-110">**Default Lock Timeout**</span></span>  
 <span data-ttu-id="8013f-111">Especifique o intervalo padrão, em milissegundos, que uma transação esperará por um bloqueio.</span><span class="sxs-lookup"><span data-stu-id="8013f-111">Specify the default interval, in milliseconds, that a transaction will wait for a lock.</span></span>  
  
 <span data-ttu-id="8013f-112">**Intervalo de Liberação**</span><span class="sxs-lookup"><span data-stu-id="8013f-112">**Flush Interval**</span></span>  
 <span data-ttu-id="8013f-113">Especifique o intervalo, em segundos, entre transações confirmadas para liberar os dados para o disco.</span><span class="sxs-lookup"><span data-stu-id="8013f-113">Specify the interval, in seconds, between committed transactions to flush data to disk.</span></span>  
  
 <span data-ttu-id="8013f-114">**Identificador de Localidade**</span><span class="sxs-lookup"><span data-stu-id="8013f-114">**Locale Identifier**</span></span>  
 <span data-ttu-id="8013f-115">Especifique a LCID (Identificação de Localidade) no banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="8013f-115">Specify the Locale ID (LCID) of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="8013f-116">**Tamanho Máximo do Buffer**</span><span class="sxs-lookup"><span data-stu-id="8013f-116">**Max Buffer Size**</span></span>  
 <span data-ttu-id="8013f-117">Especifique a quantidade máxima de memória, em quilobytes, que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact usa antes de liberar os dados para o disco.</span><span class="sxs-lookup"><span data-stu-id="8013f-117">Specify the maximum amount of memory, in kilobytes, that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact uses before flushing data to disk.</span></span>  
  
 <span data-ttu-id="8013f-118">**Tamanho Máximo do Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="8013f-118">**Max Database Size**</span></span>  
 <span data-ttu-id="8013f-119">Especifique o tamanho máximo, em megabytes, do banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="8013f-119">Specify the maximum size, in megabytes, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="8013f-120">**Modo**</span><span class="sxs-lookup"><span data-stu-id="8013f-120">**Mode**</span></span>  
 <span data-ttu-id="8013f-121">Especifique o modo de arquivo no qual abrir o banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="8013f-121">Specify the file mode in which to open the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="8013f-122">O valor padrão dessa propriedade é **Leitura Gravação**.</span><span class="sxs-lookup"><span data-stu-id="8013f-122">The default value for this property is **Read Write**.</span></span>  
  
 <span data-ttu-id="8013f-123">A opção Modo tem quatro valores, como descrito na tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="8013f-123">The Mode option has four values, as described in the following table.</span></span>  
  
|<span data-ttu-id="8013f-124">Valor</span><span class="sxs-lookup"><span data-stu-id="8013f-124">Value</span></span>|<span data-ttu-id="8013f-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="8013f-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8013f-126">**Somente Leitura**</span><span class="sxs-lookup"><span data-stu-id="8013f-126">**Read Only**</span></span>|<span data-ttu-id="8013f-127">Especifica acesso somente de leitura ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8013f-127">Specifies read-only access to the database.</span></span>|  
|<span data-ttu-id="8013f-128">**Leitura/gravação**</span><span class="sxs-lookup"><span data-stu-id="8013f-128">**Read Write**</span></span>|<span data-ttu-id="8013f-129">Especifica a permissão de leitura e gravação ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8013f-129">Specifies read/write permission to the database.</span></span>|  
|<span data-ttu-id="8013f-130">**Exclusive**</span><span class="sxs-lookup"><span data-stu-id="8013f-130">**Exclusive**</span></span>|<span data-ttu-id="8013f-131">Especifica o acesso exclusivo ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8013f-131">Specifies exclusive access to the database.</span></span>|  
|<span data-ttu-id="8013f-132">**Shared Read**</span><span class="sxs-lookup"><span data-stu-id="8013f-132">**Shared Read**</span></span>|<span data-ttu-id="8013f-133">Especifica que outros usuários podem ler de banco de dados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8013f-133">Specifies that other users can read from the database at the same time.</span></span>|  
  
 <span data-ttu-id="8013f-134">**Persist Security Info**</span><span class="sxs-lookup"><span data-stu-id="8013f-134">**Persist Security Info**</span></span>  
 <span data-ttu-id="8013f-135">Especifique se as informações de segurança são retornadas como parte da cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="8013f-135">Specify whether security information is returned as part of the connection string.</span></span> <span data-ttu-id="8013f-136">O valor padrão dessa opção é **False**.</span><span class="sxs-lookup"><span data-stu-id="8013f-136">The default value for this option is **False**.</span></span>  
  
 <span data-ttu-id="8013f-137">**Diretório de Arquivo Temporário**</span><span class="sxs-lookup"><span data-stu-id="8013f-137">**Temp File Directory**</span></span>  
 <span data-ttu-id="8013f-138">Especifique o local do arquivo de banco de dados temporário do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="8013f-138">Specify the location of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact temporary database file.</span></span>  
  
 <span data-ttu-id="8013f-139">**Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="8013f-139">**Data Source**</span></span>  
 <span data-ttu-id="8013f-140">Especifique o nome do banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="8013f-140">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="8013f-141">**Senha**</span><span class="sxs-lookup"><span data-stu-id="8013f-141">**Password**</span></span>  
 <span data-ttu-id="8013f-142">Digite a senha para o banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="8013f-142">Enter the password for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8013f-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8013f-143">See Also</span></span>  
 <span data-ttu-id="8013f-144">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8013f-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="8013f-145">Editor do Gerenciador de Conexões do SQL Server Compact Edition &#40;Página de Conexão&#41;</span><span class="sxs-lookup"><span data-stu-id="8013f-145">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../../2014/integration-services/sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
  

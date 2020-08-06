---
title: Instância do servidor principal (Assistente para Configurar Segurança de Espelhamento de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.principalsrvr.f1
ms.assetid: 58af27d7-c5dd-4669-be6b-b472bc2c8ef4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2632b5ffd5355065b4b5c1f905b3b6e5c5b6204d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681166"
---
# <a name="principal-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="3a8fb-102">Instância do servidor principal (Assistente para Configurar Segurança de Espelhamento de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="3a8fb-102">Principal Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="3a8fb-103">Use essa página para especificar informações sobre a instância de servidor principal do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-103">Use this page to specify information about the server instance of the principal database.</span></span> <span data-ttu-id="3a8fb-104">O banco de dados principal é a cópia do banco de dados que dá início à sessão de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-104">The principal database is the copy of the database that begins the mirroring session.</span></span> <span data-ttu-id="3a8fb-105">Após o início da sessão, o banco de dados principal é a cópia do banco de dados que aceita as mudanças feitas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-105">After the session has begun, the principal database is the copy of the database that accepts user changes.</span></span> <span data-ttu-id="3a8fb-106">(Quando ocorre um failover, as funções principal e de espelhamento são trocadas. Dessa forma, o banco de dados principal inicial pode não permanecer como banco de dados principal.)</span><span class="sxs-lookup"><span data-stu-id="3a8fb-106">(When a failover occurs, the principal and mirroring roles are swapped; therefore, the initial principal database might not remain the principal database.)</span></span>  
  
 <span data-ttu-id="3a8fb-107">**Para configurar o espelhamento de banco de dados usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="3a8fb-107">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="3a8fb-108">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3a8fb-108">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="3a8fb-109">Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3a8fb-109">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="3a8fb-110">Opções</span><span class="sxs-lookup"><span data-stu-id="3a8fb-110">Options</span></span>  
 <span data-ttu-id="3a8fb-111">**Instância do servidor principal**</span><span class="sxs-lookup"><span data-stu-id="3a8fb-111">**Principal server instance**</span></span>  
 <span data-ttu-id="3a8fb-112">Como o espelhamento de banco de dados do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] é sempre configurado no servidor principal, a instância do servidor atual é sempre a instância do servidor principal.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-112">Because database mirroring in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is always configured from the principal server, the current server instance is always the principal server instance.</span></span>  
  
 <span data-ttu-id="3a8fb-113">**Porta do ouvinte**</span><span class="sxs-lookup"><span data-stu-id="3a8fb-113">**Listener Port**</span></span>  
 <span data-ttu-id="3a8fb-114">O comportamento dessa opção depende de o ponto de extremidade do espelhamento existir nessa instância do servidor, como segue:</span><span class="sxs-lookup"><span data-stu-id="3a8fb-114">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="3a8fb-115">Se não houver porta do ouvinte na instância do servidor, o número da porta 5022 será exibido na caixa de texto **Porta** .</span><span class="sxs-lookup"><span data-stu-id="3a8fb-115">If the listener port does not exist for this server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="3a8fb-116">Você pode usar qualquer número de porta disponível, como 7022.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-116">You can use any available port number, such as, 7022.</span></span>  
  
-   <span data-ttu-id="3a8fb-117">Quando o ponto de extremidade do espelhamento já existir, o número da porta daquele ponto de extremidade será exibido.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-117">When the mirroring endpoint already exists, the port number from the endpoint is displayed.</span></span> <span data-ttu-id="3a8fb-118">Se for necessário alterar a porta, use um comando ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-118">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="3a8fb-119">Para obter mais informações, consulte [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a8fb-119">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a8fb-120">É necessário um número de porta.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-120">A port number is required.</span></span>  
  
 <span data-ttu-id="3a8fb-121">**Nome do ponto de extremidade**</span><span class="sxs-lookup"><span data-stu-id="3a8fb-121">**Endpoint name**</span></span>  
 <span data-ttu-id="3a8fb-122">Se o ponto de extremidade de espelhamento existir para essa instância do servidor, o nome de ponto de extremidade será exibido aqui.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-122">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="3a8fb-123">Se o ponto de extremidade não existir, você poderá especificar o nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-123">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="3a8fb-124">**Criptografar dados enviados por esse ponto de extremidade**</span><span class="sxs-lookup"><span data-stu-id="3a8fb-124">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="3a8fb-125">Por padrão, a criptografia está habilitada.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-125">By default, encryption is enabled.</span></span> <span data-ttu-id="3a8fb-126">Quando habilitada, a criptografia é necessária (não tem meramente um suporte) e usa os valores padrão de todas as opções de criptografia.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-126">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="3a8fb-127">Para obter mais informações, veja [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a8fb-127">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="3a8fb-128">Para desabilitar a criptografia, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-128">To disable encryption, clear the check box.</span></span> <span data-ttu-id="3a8fb-129">Para habilitar a criptografia novamente, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="3a8fb-129">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8fb-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a8fb-130">See Also</span></span>  
 <span data-ttu-id="3a8fb-131">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a8fb-131">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="3a8fb-132">[Propriedades do banco de dados &#40;página Espelhamento&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="3a8fb-132">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="3a8fb-133">[Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="3a8fb-133">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="3a8fb-134">[Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3a8fb-134">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="3a8fb-135">Espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3a8fb-135">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  

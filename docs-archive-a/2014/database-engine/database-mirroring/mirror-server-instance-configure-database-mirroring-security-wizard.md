---
title: Instância do servidor espelho (Assistente para Configurar Segurança de Espelhamento de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.mirrorsrvr.f1
ms.assetid: 53223432-615e-440f-904d-925d33ec2144
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889e62af592d8d23f2aca0d752f1c7f535df883a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685923"
---
# <a name="mirror-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="61ef5-102">Instância de servidor espelho (Assistente para Configurar Segurança de Espelhamento de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="61ef5-102">Mirror Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="61ef5-103">Use esta página para especificar informações sobre a instância de servidor com o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="61ef5-103">Use this page to specify information about the server instance with the mirror database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="61ef5-104">A instância do servidor espelho deve estar executando a mesma edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Standard ou Enterprise, como a instância do servidor principal.</span><span class="sxs-lookup"><span data-stu-id="61ef5-104">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], either Standard or Enterprise, as the principal server instance.</span></span> <span data-ttu-id="61ef5-105">Além disso, é altamente recomendável que elas sejam executadas em sistemas comparáveis que possam controlar cargas de trabalho idênticas.</span><span class="sxs-lookup"><span data-stu-id="61ef5-105">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
 <span data-ttu-id="61ef5-106">**Para configurar o espelhamento de banco de dados usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="61ef5-106">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="61ef5-107">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="61ef5-107">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="61ef5-108">Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="61ef5-108">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="61ef5-109">Opções</span><span class="sxs-lookup"><span data-stu-id="61ef5-109">Options</span></span>  
 <span data-ttu-id="61ef5-110">**Instância do servidor espelho**</span><span class="sxs-lookup"><span data-stu-id="61ef5-110">**Mirror server instance**</span></span>  
 <span data-ttu-id="61ef5-111">Se uma instância de servidor espelho já for especificada (na página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** ), essa instância será exibida; para obter mais informações, veja [Propriedades do banco de dados &#40;página Espelhamento&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span><span class="sxs-lookup"><span data-stu-id="61ef5-111">If a mirror server instance is already specified (on the **Mirroring** page of the **Database Properties** dialog box), that instance is displayed; for more information, see [Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span></span>  
  
 <span data-ttu-id="61ef5-112">Caso contrário, insira o nome da instância de servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="61ef5-112">Otherwise, enter the name of the mirror server instance.</span></span> <span data-ttu-id="61ef5-113">Observe que a instância de servidor espelho não pode ser igual à instância de servidor principal.</span><span class="sxs-lookup"><span data-stu-id="61ef5-113">Note that the mirror server instance cannot be the same as the principal server instance.</span></span>  
  
 <span data-ttu-id="61ef5-114">**Connect**</span><span class="sxs-lookup"><span data-stu-id="61ef5-114">**Connect**</span></span>  
 <span data-ttu-id="61ef5-115">Se uma instância de servidor espelho não foi especificada, clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="61ef5-115">If a mirror server instance has not been specified, click **Connect**.</span></span> <span data-ttu-id="61ef5-116">Isso exibe a caixa de diálogo **Conectar ao Servidor** na qual você pode especificar a instância de servidor e estabelecer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="61ef5-116">This displays the **Connect to Server** dialog box in which you can specify the server instance and establish a connection.</span></span>  
  
 <span data-ttu-id="61ef5-117">Se a instância foi especificada, mas o assistente não tem uma conexão com permissão suficiente para verificar a existência do ponto de extremidade, clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="61ef5-117">If the instance has been specified, but the wizard lacks a connection with sufficient permission to check for the existence of the endpoint, click **Connect**.</span></span> <span data-ttu-id="61ef5-118">Isso exibe a caixa de diálogo **Conectar ao Servidor** com a instância de servidor pré-selecionada e inalterável.</span><span class="sxs-lookup"><span data-stu-id="61ef5-118">This displays the **Connect to Server** dialog box with the server instance pre-selected and unchangeable.</span></span> <span data-ttu-id="61ef5-119">Especifique uma conta de domínio com permissão suficiente e conecte-se à instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="61ef5-119">Specify a domain account with sufficient permission, and connect to the server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61ef5-120">Ao conectar-se à instância de servidor, o Assistente para Configurar Segurança de Espelhamento de Banco de Dados usa as credenciais fornecidas na caixa de diálogo **Conectar ao Servidor** .</span><span class="sxs-lookup"><span data-stu-id="61ef5-120">When connecting to the server instance, the Configure Database Mirroring Security Wizard uses the credentials provided in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="61ef5-121">Essas credenciais são diferentes de uma sessão de espelhamento, que usa as credenciais da conta de inicialização onde a instância de servidor está sendo executada como um serviço.</span><span class="sxs-lookup"><span data-stu-id="61ef5-121">These are different from the credentials of a mirroring session, which uses the credentials of the startup account where the server instance is running as a service.</span></span>  
  
 <span data-ttu-id="61ef5-122">**Porta do ouvinte**</span><span class="sxs-lookup"><span data-stu-id="61ef5-122">**Listener Port**</span></span>  
 <span data-ttu-id="61ef5-123">O comportamento dessa opção depende de o ponto de extremidade do espelhamento existir nessa instância do servidor, como segue:</span><span class="sxs-lookup"><span data-stu-id="61ef5-123">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="61ef5-124">Se uma porta do ouvinte não existir para a instância de servidor, o número da porta 5022 será exibido na caixa de texto **Porta** .</span><span class="sxs-lookup"><span data-stu-id="61ef5-124">If a listener port does not exist for the server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="61ef5-125">Você pode usar qualquer número de porta disponível, como 7022.</span><span class="sxs-lookup"><span data-stu-id="61ef5-125">You can use any available port number, such as 7022.</span></span>  
  
-   <span data-ttu-id="61ef5-126">Quando o ponto de extremidade do espelhamento já existir, o número da porta daquele ponto de extremidade é exibido.</span><span class="sxs-lookup"><span data-stu-id="61ef5-126">When the mirroring endpoint already exists, the port number from that endpoint is displayed.</span></span> <span data-ttu-id="61ef5-127">Se for necessário alterar a porta, use um comando ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="61ef5-127">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="61ef5-128">Para obter mais informações, consulte [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61ef5-128">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61ef5-129">É necessário um número de porta.</span><span class="sxs-lookup"><span data-stu-id="61ef5-129">A port number is required.</span></span>  
  
 <span data-ttu-id="61ef5-130">**Nome do ponto de extremidade**</span><span class="sxs-lookup"><span data-stu-id="61ef5-130">**Endpoint name**</span></span>  
 <span data-ttu-id="61ef5-131">Se o ponto de extremidade de espelhamento existir para essa instância do servidor, o nome de ponto de extremidade será exibido aqui.</span><span class="sxs-lookup"><span data-stu-id="61ef5-131">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="61ef5-132">Se o ponto de extremidade não existir, você poderá especificar o nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="61ef5-132">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="61ef5-133">**Criptografar dados enviados por esse ponto de extremidade**</span><span class="sxs-lookup"><span data-stu-id="61ef5-133">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="61ef5-134">Por padrão, a criptografia está habilitada.</span><span class="sxs-lookup"><span data-stu-id="61ef5-134">By default, encryption is enabled.</span></span> <span data-ttu-id="61ef5-135">Quando habilitada, a criptografia é necessária (não tem meramente um suporte) e usa os valores padrão de todas as opções de criptografia.</span><span class="sxs-lookup"><span data-stu-id="61ef5-135">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="61ef5-136">Para obter mais informações, veja [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="61ef5-136">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="61ef5-137">Para desabilitar a criptografia, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="61ef5-137">To disable encryption, clear the check box.</span></span> <span data-ttu-id="61ef5-138">Para habilitar a criptografia novamente, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="61ef5-138">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ef5-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61ef5-139">See Also</span></span>  
 <span data-ttu-id="61ef5-140">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="61ef5-140">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="61ef5-141">[Propriedades do banco de dados &#40;página Espelhamento&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="61ef5-141">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="61ef5-142">[Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="61ef5-142">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="61ef5-143">[Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="61ef5-143">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="61ef5-144">Espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="61ef5-144">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  

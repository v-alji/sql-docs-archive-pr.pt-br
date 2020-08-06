---
title: Criar e editar um serviço Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- createSrv
ms.assetid: 10cd612e-d8f1-4af2-97d3-a0c22e1e2326
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3325e272285895e813f01d50a1c312e75472919b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572142"
---
# <a name="create-and-edit-an-oracle-cdc-service"></a><span data-ttu-id="e2bc6-102">Criar e editar um Serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="e2bc6-102">Create and Edit an Oracle CDC Service</span></span>
  <span data-ttu-id="e2bc6-103">Você cria e edita um novo Serviço do Windows do Oracle CDC a partir do Console de Configuração do Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-103">You create and edit a new Oracle CDC Windows Service from the CDC Service Configuration Console.</span></span>  
  
 <span data-ttu-id="e2bc6-104">Para criar um novo Serviço do Windows do Oracle CDC, selecione **Serviços Locais de CDC** no painel esquerdo e clique em **Novo Serviço** no painel **Ações** .</span><span class="sxs-lookup"><span data-stu-id="e2bc6-104">To create a new Oracle CDC Windows service, select **Local CDC Services** from the left pane, then click **New Service** from the **Actions** pane.</span></span> <span data-ttu-id="e2bc6-105">Você também pode clicar com o botão direito do mouse em **Serviços Locais de CDC** e selecionar **Novo Serviço**.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-105">You can also right-click **Local CDC Services** and select **New Service**.</span></span> <span data-ttu-id="e2bc6-106">O caixa de diálogo Novo Serviço do Windows do Oracle CDC é aberta.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-106">The New Oracle CDC Windows Service dialog box opens.</span></span>  
  
 <span data-ttu-id="e2bc6-107">**OR**</span><span class="sxs-lookup"><span data-stu-id="e2bc6-107">**OR**</span></span>  
  
 <span data-ttu-id="e2bc6-108">Para editar as propriedade de serviço CDC, selecione o serviço para o qual você deseja editar as propriedades e clique em **Propriedades** no painel **Ações** .</span><span class="sxs-lookup"><span data-stu-id="e2bc6-108">To edit the CDC service properties, select the service that you want to edit the properties for and click **Properties** from the **Actions** pane.</span></span> <span data-ttu-id="e2bc6-109">Você também pode clicar com o botão direito do mouse no serviço com o qual você está trabalhando e selecionar **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-109">You can also right-click the service you are working with and select **Properties**.</span></span> <span data-ttu-id="e2bc6-110">A caixa de diálogo Propriedades do Serviço CDC será aberta.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-110">The CDC Service Properties dialog box opens.</span></span>  
  
 <span data-ttu-id="e2bc6-111">Insira as informações a seguir na caixa de diálogo Novo Serviço do Windows do Oracle CDC ou na caixa de diálogo Propriedades de Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-111">Enter the following information in the New Oracle CDC Windows Service dialog box or the CDC Service Properties dialog box.</span></span>  
  
 <span data-ttu-id="e2bc6-112">Nome do Serviço</span><span class="sxs-lookup"><span data-stu-id="e2bc6-112">Service Name</span></span>  
 <span data-ttu-id="e2bc6-113">Digite o nome do novo Serviço do Windows do Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-113">Type the name of the new Oracle CDC Windows Service.</span></span> <span data-ttu-id="e2bc6-114">Você não deve usar nomes longos, se possível.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-114">You should not use long names, if possible.</span></span> <span data-ttu-id="e2bc6-115">Os caracteres / e \ não podem ser usados no nome de serviço.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-115">The characters / and \ cannot be used in the service name.</span></span>  
  
> [!NOTE]  
> <span data-ttu-id="e2bc6-116">Esta opção não está disponível ao editar o serviço.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-116">This option is not available when editing the service.</span></span> <span data-ttu-id="e2bc6-117">Você não pode alterar o nome de um Serviço do Windows que já exist.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-117">You cannot change the name of a Windows service that already exists.</span></span>  
  
 <span data-ttu-id="e2bc6-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e2bc6-118">**Description**</span></span>  
 <span data-ttu-id="e2bc6-119">Digite uma descrição do serviço para ajudar a identificá-lo.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-119">Type a description of the service to help identify it.</span></span>  
  
 <span data-ttu-id="e2bc6-120">**Conta de Serviço**</span><span class="sxs-lookup"><span data-stu-id="e2bc6-120">**Service Account**</span></span>  
 <span data-ttu-id="e2bc6-121">Selecione um dos seguintes para determinar sob qual conta se deve executar o serviço:</span><span class="sxs-lookup"><span data-stu-id="e2bc6-121">Select one of the following to determine under which account to run the service:</span></span>  
  
-   <span data-ttu-id="e2bc6-122">**Conta Sistema Local**</span><span class="sxs-lookup"><span data-stu-id="e2bc6-122">**Local System Account**</span></span>  
  
     <span data-ttu-id="e2bc6-123">Isto não é recomendado porque dá permissões demais ao serviço.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-123">This is not recommended because it gives too many permissions to the service.</span></span>  
  
-   <span data-ttu-id="e2bc6-124">**Esta conta**</span><span class="sxs-lookup"><span data-stu-id="e2bc6-124">**This Account**</span></span>  
  
     <span data-ttu-id="e2bc6-125">No Windows Vista ou Windows Server 2008, a conta de serviço padrão é NETWORK SERVICE.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-125">On Windows Vista or Windows Server 2008, the default service account is the NETWORK SERVICE account.</span></span>  
  
     <span data-ttu-id="e2bc6-126">No Windows 7, Windows Server 2008 R2 e posterior, a conta de serviço padrão é NT Service\\<service-name>.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-126">On Windows 7, Windows Server 2008 R2 and later, the default service account is NT Service\\<service-name>.</span></span>  
  
     <span data-ttu-id="e2bc6-127">Usar estas contas permite que você trabalhe sem usar senhas, porque uma senha não é necessária para estas contas.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-127">Using these accounts lets you work without using passwords because a password is not necessary for these accounts.</span></span> <span data-ttu-id="e2bc6-128">Além disso, estas contas fornecem somente as permissões exigidas necessárias para que o Serviço Oracle CDC seja executado.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-128">In addition these accounts provide only the necessary permissions required for the Oracle CDC Service to run.</span></span>  
  
     <span data-ttu-id="e2bc6-129">Você pode usar uma conta do Windows local ou de domínio para a conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-129">You can use a local or domain Windows account for the service account.</span></span> <span data-ttu-id="e2bc6-130">Neste caso, você deve inserir a **Senha** para essa conta.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-130">In this case, you must enter the **Password** for that account.</span></span> <span data-ttu-id="e2bc6-131">Esta conta pode ser para o host local ou uma conta de domínio.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-131">This account can be for the local host or a domain account.</span></span> <span data-ttu-id="e2bc6-132">Atualize a senha quando ela for alterada usando os Serviços Locais no Painel de Controle do Windows.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-132">Be sure to update the password when it is changed using Local Services in the Windows Control Panel.</span></span>  
  
 <span data-ttu-id="e2bc6-133">**Nome do servidor**: selecione a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino para se conectar (por exemplo, **\\\\<nome_do_computador>\\<nome_da_instância>** ).</span><span class="sxs-lookup"><span data-stu-id="e2bc6-133">**Server name**: Select the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to connect to (for example, **\\\\<computer_name>\\<instance_name>**).</span></span> <span data-ttu-id="e2bc6-134">Por padrão, é exibida a instância de servidor usada na última conexão.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-134">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="e2bc6-135">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="e2bc6-135">**Authentication**</span></span>  
 <span data-ttu-id="e2bc6-136">Selecione uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="e2bc6-136">Select one of the following:</span></span>  
  
-   <span data-ttu-id="e2bc6-137">**Autenticação do Windows**: se você selecionar esta opção, o serviço Oracle CDC se conectará à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino usando a identidade da conta de serviço.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-137">**Windows Authentication**: If you select this option, the Oracle CDC service connects to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using the service account identity.</span></span> <span data-ttu-id="e2bc6-138">Se a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver sendo executada em um computador diferente, a Autenticação do Windows deverá ser usada com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-138">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is running on a different computer, Windows Authentication must be used with domain accounts.</span></span>  
  
-   <span data-ttu-id="e2bc6-139">**Autenticação do SQL Server**: se você selecionar esta opção, deverá digitar o **Nome de usuário** e **Senha** para o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-139">**SQL Server Authentication**: If you select this option, you must type the **User Name** and **Password** for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login you want to use.</span></span> <span data-ttu-id="e2bc6-140">O serviço Oracle CDC usa estas credenciais ao conectar-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-140">The Oracle CDC service uses these credentials when connecting to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="e2bc6-141">O logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado pelo Serviço Oracle CDC somente precisa ser um membro da função pública de servidor fixa, nenhum outro privilégio será necessário.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-141">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Oracle CDC Service only needs to be a member of the public fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="e2bc6-142">Quando novas Instâncias Oracle CDC são adicionadas, esse logon ganhará acesso **db_owner** aos bancos de dados CDC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associados.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-142">Once new Oracle CDC Instances are added, that login will gain **db_owner** access to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC databases.</span></span>  
  
 <span data-ttu-id="e2bc6-143">Para criar a definição de Serviço do Windows do Oracle CDC, o programa precisa de acesso de atualização ao banco de dados MSXDBCDC na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associada.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-143">To create the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="e2bc6-144">Quando você clica em **OK**, uma caixa de diálogo solicita que o usuário insira um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com um acesso de atualização para o banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-144">When you click **OK**, a dialog box prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="e2bc6-145">Para obter informações sobre os dados que você deverá digitar na caixa de diálogo Conecte-se ao SQL Server, consulte [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e2bc6-145">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
 <span data-ttu-id="e2bc6-146">**Opções**</span><span class="sxs-lookup"><span data-stu-id="e2bc6-146">**Options**</span></span>  
 <span data-ttu-id="e2bc6-147">Clique na seta para exibir opções disponíveis a serem configuradas.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-147">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="e2bc6-148">Você pode escolher deixar estas opções com o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-148">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="e2bc6-149">As opções disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="e2bc6-149">The available options are:</span></span>  
  
-   <span data-ttu-id="e2bc6-150">**Tempo limite da conexão**: Digite o tempo (em segundos) que o Serviço CDC para Oracle espera por uma conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de exceder o tempo limite. O valor padrão é **15**.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-150">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="e2bc6-151">**Tempo limite de execução**: Digite o tempo (em segundos) que o Serviço do Windows do Oracle CDC espera que um comando seja executado antes de exceder o tempo limite. O valor padrão é **30**.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-151">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="e2bc6-152">**Criptografar conexão**: selecione **Criptografar Conexão** para a comunicação entre o Serviço Oracle CDC e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino usando uma conexão criptografada.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-152">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="e2bc6-153">**Avançado**: digite as propriedades de conexão adicionais, se necessário.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-153">**Advanced**: Type any additional connection properties, if necessary.</span></span>  
  
 <span data-ttu-id="e2bc6-154">**Senha mestra**</span><span class="sxs-lookup"><span data-stu-id="e2bc6-154">**Master Password**</span></span>  
 <span data-ttu-id="e2bc6-155">Insira uma senha a ser usada pelo Serviço do Windows do Oracle CDC para proteger as credenciais da mineração de logs do Oracle.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-155">Enter a password to be used by the Oracle CDC Windows Service to protect the Oracle log-mining credentials.</span></span>  
  
 <span data-ttu-id="e2bc6-156">A mesma senha mestre também deve ser usada quando outras instâncias são configuradas do mesmo serviço em outros nós em um cluster em configuração de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-156">The same master password must also be used when other instances of the same service are configured on other nodes on a cluster in high-availability configuration.</span></span> <span data-ttu-id="e2bc6-157">Se você perder ou modificar a senha mestra, todas as senhas de mineração de logs armazenadas em bancos de dados de Instância Oracle CDC devem ser reinseridas usando o CDC Designer Console.</span><span class="sxs-lookup"><span data-stu-id="e2bc6-157">If you lose or modify the master password, all log mining passwords stored in Oracle CDC Instance databases must be re-entered using the CDC Designer console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2bc6-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2bc6-158">See Also</span></span>  
 [<span data-ttu-id="e2bc6-159">Como criar e editar um serviço CDC</span><span class="sxs-lookup"><span data-stu-id="e2bc6-159">How to Create and Edit a CDC Service</span></span>](how-to-create-and-edit-a-cdc-service.md)  
  
  

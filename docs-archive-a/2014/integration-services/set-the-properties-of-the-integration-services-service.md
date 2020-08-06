---
title: Definir as propriedades do serviço de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- Integration Services service, properties
ms.assetid: 3a8ad546-0f58-4b31-ab56-58d6313b1098
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 055eadd9a1d59c59dd40675b142eae480763f6f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685828"
---
# <a name="set-the-properties-of-the-integration-services-service"></a><span data-ttu-id="16781-102">Definir as propriedades do serviço do Integration Services</span><span class="sxs-lookup"><span data-stu-id="16781-102">Set the Properties of the Integration Services Service</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="16781-103">Esse tópico discute o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , um serviço do Windows para o gerenciamento de pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16781-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="16781-104">dá suporte ao serviço para compatibilidade de versões anteriores com versões anteriores do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16781-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="16781-105">A partir do [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], você pode gerenciar objetos como pacotes no servidor do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="16781-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="16781-106">O serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gerencia e monitora pacotes no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16781-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages and monitors packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="16781-107">Quando você instala o pela primeira vez [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] serviço é iniciado e o tipo de inicialização do serviço é definido como automático.</span><span class="sxs-lookup"><span data-stu-id="16781-107">When you first install [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span>  
  
 <span data-ttu-id="16781-108">Após a instalação do serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , você pode definir as propriedades do serviço usando o SQL Server Configuration Manager ou o snap-in MMC dos Serviços.</span><span class="sxs-lookup"><span data-stu-id="16781-108">After the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has been installed, you can set the properties of the service by using either SQL Server Configuration Manager or the Services MMC snap-in.</span></span>  
  
 <span data-ttu-id="16781-109">Para configurar outros recursos importantes do serviço, incluindo os locais onde armazena e gerencia pacotes, é necessário modificar o arquivo de configuração do serviço.</span><span class="sxs-lookup"><span data-stu-id="16781-109">To configure other important features of the service, including the locations where it stores and manages packages, you must modify the configuration file of the service.</span></span> <span data-ttu-id="16781-110">Para obter mais informações, consulte [Configurando o Serviço Integration Services &#40;Serviço SSIS#41;](service/integration-services-service-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="16781-110">For more information, see [Configuring the Integration Services Service &#40;SSIS Service&#41;](service/integration-services-service-ssis-service.md).</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-sql-server-configuration-manager"></a><span data-ttu-id="16781-111">Para definir propriedades do serviço do Integration Services usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="16781-111">To set properties of the Integration Services service by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="16781-112">No menu **Iniciar** , aponte para **Todos os Programas**, **Microsoft SQL Server**, **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="16781-112">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="16781-113">No snap-in **SQL Server Configuration Manager** , localize **SQL Server Integration Services** na lista de serviços, clique com o botão direito do mouse em **SQL Server Integration Services**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="16781-113">In the **SQL Server Configuration Manager** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="16781-114">Na caixa de diálogo **Propriedades de SQL Server Integration Services** , você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16781-114">In the **SQL Server Integration Services Properties** dialog box you can do the following:</span></span>  
  
    -   <span data-ttu-id="16781-115">Clique na guia **Fazer Logon** para exibir informações de logon, como o nome de conta.</span><span class="sxs-lookup"><span data-stu-id="16781-115">Click the **Log On** tab to view the logon information such as the account name.</span></span>  
  
    -   <span data-ttu-id="16781-116">Clique na guia **Serviço** para exibir informações sobre o serviço, como o nome do computador host, e para especificar o modo inicial do serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16781-116">Click the **Service** tab to view information about the service such as the name of the host computer and to specify the start mode of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="16781-117">A guia **Avançado** não contém nenhuma informação do serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16781-117">The **Advanced** tab contains no information for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
4.  <span data-ttu-id="16781-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="16781-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="16781-119">No menu **Arquivo** , clique em **Sair** para fechar o snap-in **SQL Server Configuration Manager** .</span><span class="sxs-lookup"><span data-stu-id="16781-119">On the **File** menu, click **Exit** to close the **SQL Server Configuration Manager** snap-in.</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-services"></a><span data-ttu-id="16781-120">Para definir as propriedades do serviço do Integration Services usando Serviços</span><span class="sxs-lookup"><span data-stu-id="16781-120">To set properties of the Integration Services service by using Services</span></span>  
  
1.  <span data-ttu-id="16781-121">No **Painel de Controle**, se você estiver usando o Modo de exibição Clássico, clique em **Ferramentas Administrativas**ou, se estiver usando o Modo exibição de Categoria, clique em **Desempenho e Manutenção** e em **Ferramentas Administrativas**.</span><span class="sxs-lookup"><span data-stu-id="16781-121">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="16781-122">Clique em **Serviços**.</span><span class="sxs-lookup"><span data-stu-id="16781-122">Click **Services**.</span></span>  
  
3.  <span data-ttu-id="16781-123">No snap-in **Serviços** , localize **SQL Server Integration Services** na lista de serviços, clique com o botão direito do mouse em **SQL Server Integration Services**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="16781-123">In the **Services** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="16781-124">Na caixa de diálogo **Propriedades do SQL Server Integration Services** , você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16781-124">In the **SQL Server Integration Services Properties** dialog box, you can do the following:</span></span>  
  
    -   <span data-ttu-id="16781-125">Clique na guia **geral** . Para habilitar o serviço, selecione o tipo de inicialização manual ou automática.</span><span class="sxs-lookup"><span data-stu-id="16781-125">Click the **General** tab. To enable the service, select either the manual or automatic startup type.</span></span> <span data-ttu-id="16781-126">Para desabilitar o serviço, selecione Desabilitar na caixa **Tipo de inicialização** .</span><span class="sxs-lookup"><span data-stu-id="16781-126">To disable the service, select Disable in the **Startup type** box.</span></span> <span data-ttu-id="16781-127">A seleção de Desabilitar não interromperá o serviço se ele estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="16781-127">Selecting Disable does not stop the service if it is currently running.</span></span>  
  
         <span data-ttu-id="16781-128">Se o serviço já estiver habilitado, você poderá clicar em **Parar** para interromper o serviço ou clicar em **Iniciar** para iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="16781-128">If the service is already enabled, you can click **Stop** to stop the service, or click **Start** to start the service.</span></span>  
  
    -   <span data-ttu-id="16781-129">Clique na guia **Fazer Logon** para exibir ou editar as informações de logon.</span><span class="sxs-lookup"><span data-stu-id="16781-129">Click the **Log On** tab to view or edit the logon information.</span></span>  
  
    -   <span data-ttu-id="16781-130">Clique na guia **Recuperação** para exibir as respostas do computador padrão para a falha de serviço.</span><span class="sxs-lookup"><span data-stu-id="16781-130">Click the **Recovery** tab to view the default computer responses to service failure.</span></span> <span data-ttu-id="16781-131">Você pode modificar essas opções para adequar ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="16781-131">You can modify these options to suit your environment.</span></span>  
  
    -   <span data-ttu-id="16781-132">Clique na guia **Dependências** para exibir uma lista de serviços dependentes.</span><span class="sxs-lookup"><span data-stu-id="16781-132">Click the **Dependencies** tab to view a list of dependent services.</span></span> <span data-ttu-id="16781-133">O serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] não tem nenhuma dependência.</span><span class="sxs-lookup"><span data-stu-id="16781-133">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has no dependencies.</span></span>  
  
5.  <span data-ttu-id="16781-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="16781-134">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="16781-135">Opcionalmente, se o tipo de inicialização for Manual ou Automático, você poderá clicar com o botão direito do mouse em **SQL Server Integration Services** e clicar em **Iniciar, Parar ou Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="16781-135">Optionally, if the startup type is Manual or Automatic, you can right-click **SQL Server Integration Services** and click **Start, Stop, or Restart**.</span></span>  
  
7.  <span data-ttu-id="16781-136">No menu **Arquivo** , clique em **Sair** para fechar o snap-in **Serviços** .</span><span class="sxs-lookup"><span data-stu-id="16781-136">On the **File** menu, click **Exit** to close the **Services** snap-in.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16781-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16781-137">See Also</span></span>  
 [<span data-ttu-id="16781-138">Gerenciar o serviço Integration Services</span><span class="sxs-lookup"><span data-stu-id="16781-138">Manage the Integration Services Service</span></span>](../../2014/integration-services/manage-the-integration-services-service.md)  
  
  

---
title: Administrar servidores com o SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], servers
- servers [SQL Server], administering
ms.assetid: 938bb035-e07a-4082-9f93-229d9feb6b06
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb2a6b9afba7d838cf71144f88ed7866c54ad796
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683927"
---
# <a name="administer-servers-with-sql-server-management-studio"></a><span data-ttu-id="9d561-102">Gerenciar servidores com o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9d561-102">Administer Servers with SQL Server Management Studio</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="9d561-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]o é um cliente administrativo avançado e integrado projetado para atender aos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requisitos de gerenciamento de servidor do administrador.</span><span class="sxs-lookup"><span data-stu-id="9d561-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] is a rich, integrated administrative client designed to meet the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] administrator's server management requirements.</span></span> <span data-ttu-id="9d561-104">No [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], as tarefas administrativas são realizadas com o Pesquisador de Objetos, que permite conectar-se a qualquer servidor da família [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e procurar conteúdo de forma gráfica.</span><span class="sxs-lookup"><span data-stu-id="9d561-104">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], administrative tasks are accomplished using Object Explorer, which allows you to connect to any server in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] family and graphically browse its contents.</span></span> <span data-ttu-id="9d561-105">Um servidor pode ser uma instância do [!INCLUDE[ssDE](../includes/ssde-md.md)], do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d561-105">A server can be an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9d561-106">Os componentes de ferramentas do [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] incluem os Servidores Registrados, o Pesquisador de Objetos, o Gerenciador de Soluções, o Explorador de Modelos, a página Detalhes do Pesquisador de Objetos e a janela de documentos.</span><span class="sxs-lookup"><span data-stu-id="9d561-106">The tool components of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] include Registered Servers, Object Explorer, Solution Explorer, Template Explorer, the Object Explorer Details page, and the document window.</span></span> <span data-ttu-id="9d561-107">Para exibir uma ferramenta, no menu **Exibir** , clique no nome da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="9d561-107">To display a tool, on the **View** menu, click the tool name.</span></span> <span data-ttu-id="9d561-108">Para exibir a ferramenta Editor de Consultas, clique no botão **Nova Consulta** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="9d561-108">To display the Query Editor tool, click the **New Query** button on the toolbar.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9d561-109">O tráfego de rede entre o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] e o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não é criptografado por padrão.</span><span class="sxs-lookup"><span data-stu-id="9d561-109">Network traffic between [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is unencrypted by default.</span></span> <span data-ttu-id="9d561-110">Não trabalhe com dados confidenciais (inclusive senhas) no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] a menos que você tenha definido uma conexão criptografada.</span><span class="sxs-lookup"><span data-stu-id="9d561-110">Do not work with sensitive data (including passwords) in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] unless you have established an encrypted connection.</span></span> <span data-ttu-id="9d561-111">Para obter mais informações, veja [Habilitar conexões criptografadas no Mecanismo de Banco de Dados &#40;SQL Server Configuration Manager&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="9d561-111">For more information, see [Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span></span>  
  
 <span data-ttu-id="9d561-112">Use o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para:</span><span class="sxs-lookup"><span data-stu-id="9d561-112">Use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="9d561-113">Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="9d561-113">Register servers.</span></span>  
  
-   <span data-ttu-id="9d561-114">Conectar-se a uma instância do [!INCLUDE[ssDE](../includes/ssde-md.md)], do [!INCLUDE[ssAS](../includes/ssas-md.md)], do [!INCLUDE[ssRS](../includes/ssrs.md)] ou do [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d561-114">Connect to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)], or [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
-   <span data-ttu-id="9d561-115">Configurar propriedades de servidor.</span><span class="sxs-lookup"><span data-stu-id="9d561-115">Configure server properties.</span></span>  
  
-   <span data-ttu-id="9d561-116">Gerenciar banco de dados e objetos [!INCLUDE[ssAS](../includes/ssas-md.md)] , como cubos, dimensões e assemblies.</span><span class="sxs-lookup"><span data-stu-id="9d561-116">Manage database and [!INCLUDE[ssAS](../includes/ssas-md.md)] objects such as cubes, dimensions, and assemblies.</span></span>  
  
-   <span data-ttu-id="9d561-117">Criar objetos, como bancos de dados, tabelas, cubos, usuários de banco de dados e logons.</span><span class="sxs-lookup"><span data-stu-id="9d561-117">Create objects, such as databases, tables, cubes, database users, and logins.</span></span>  
  
-   <span data-ttu-id="9d561-118">Administrar arquivos e grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d561-118">Manage files and filegroups.</span></span>  
  
-   <span data-ttu-id="9d561-119">Anexar ou desanexar bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="9d561-119">Attach or detach databases.</span></span>  
  
-   <span data-ttu-id="9d561-120">Iniciar ferramentas de script.</span><span class="sxs-lookup"><span data-stu-id="9d561-120">Launch scripting tools.</span></span>  
  
-   <span data-ttu-id="9d561-121">Administrar segurança.</span><span class="sxs-lookup"><span data-stu-id="9d561-121">Manage security.</span></span>  
  
-   <span data-ttu-id="9d561-122">Exibir logs do sistema.</span><span class="sxs-lookup"><span data-stu-id="9d561-122">View system logs.</span></span>  
  
-   <span data-ttu-id="9d561-123">Monitorar a atividade atual.</span><span class="sxs-lookup"><span data-stu-id="9d561-123">Monitor current activity.</span></span>  
  
-   <span data-ttu-id="9d561-124">Configurar replicação.</span><span class="sxs-lookup"><span data-stu-id="9d561-124">Configure replication.</span></span>  
  
-   <span data-ttu-id="9d561-125">Administrar índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="9d561-125">Manage full-text indexes.</span></span>  
  
 <span data-ttu-id="9d561-126">Para iniciar e parar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, use o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9d561-126">To start and stop [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d561-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d561-127">See Also</span></span>  
 <span data-ttu-id="9d561-128">[Usar SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="9d561-128">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="9d561-129">Exibir ou alterar as propriedades de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9d561-129">View or Change Server Properties &#40;SQL Server&#41;</span></span>](../database-engine/configure-windows/view-or-change-server-properties-sql-server.md)  
  
  

---
title: Renomear um computador do servidor de relatório | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- renaming report servers
ms.assetid: 82fc4ba2-291a-4939-a025-271b8d687c54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe8f699c17f9e5f1e11406ac6e5c161488767ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583379"
---
# <a name="rename-a-report-server-computer"></a><span data-ttu-id="da6d2-102">Renomear um computador de servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="da6d2-102">Rename a Report Server Computer</span></span>
  <span data-ttu-id="da6d2-103">A renomeação de um computador provoca uma alteração de nome correspondente para o servidor Web e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (se estiver no mesmo computador).</span><span class="sxs-lookup"><span data-stu-id="da6d2-103">Renaming a computer causes a corresponding name change for the Web server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (if it is on the same computer).</span></span> <span data-ttu-id="da6d2-104">Em alguns casos, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] talvez não possa ser acessado após uma alteração de nome do computador.</span><span class="sxs-lookup"><span data-stu-id="da6d2-104">In some cases, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] may not be accessible after a computer name change.</span></span> <span data-ttu-id="da6d2-105">Use as etapas fornecidas neste tópico para reconfigurar um servidor de relatório depois de uma alteração de nome do computador.</span><span class="sxs-lookup"><span data-stu-id="da6d2-105">Use the steps provided in this topic to reconfigure a report server after a computer name change.</span></span>  
  
## <a name="renaming-a-sql-server-database-engine"></a><span data-ttu-id="da6d2-106">Renomeando um Mecanismo de Banco de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="da6d2-106">Renaming a SQL Server Database Engine</span></span>  
 <span data-ttu-id="da6d2-107">Se você renomear a instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que executa o banco de dados do servidor de relatório, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="da6d2-107">If you rename the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance that runs the report server database, do the following:</span></span>  
  
1.  <span data-ttu-id="da6d2-108">Inicie a ferramenta Configuração do Reporting Services e conecte-se ao servidor de relatório que usa o banco de dados do servidor de relatório no servidor renomeado.</span><span class="sxs-lookup"><span data-stu-id="da6d2-108">Start the Reporting Services Configuration tool and connect to the report server that uses the report server database on the renamed server.</span></span>  
  
2.  <span data-ttu-id="da6d2-109">Abra a página Configuração do Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="da6d2-109">Open the Database Setup page.</span></span>  
  
3.  <span data-ttu-id="da6d2-110">Em **Nome do Servidor**, digite ou selecione o nome do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e, em seguida, clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="da6d2-110">In **Server Name**, type or select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="da6d2-111">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="da6d2-111">Click **Apply**.</span></span>  
  
 <span data-ttu-id="da6d2-112">Se o servidor de relatório estiver usando uma instância local do [!INCLUDE[ssDE](../../includes/ssde-md.md)] , use *(local)* ou *(local)\nomedainstância* para especificar o servidor.</span><span class="sxs-lookup"><span data-stu-id="da6d2-112">If the report server is using a local [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, you can use *(local)* or *(local)\instancename* to specify the server.</span></span> <span data-ttu-id="da6d2-113">Se você usar *(local)* para fazer referência ao servidor, poderá renomear o servidor e as conexões continuarão funcionando.</span><span class="sxs-lookup"><span data-stu-id="da6d2-113">If you use *(local)* to refer to the server, you can rename the server and the connections will continue to work.</span></span> <span data-ttu-id="da6d2-114">Caso esteja usando um servidor remoto ou o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] seja configurado com o nome do servidor, atualize as informações de conexão do banco de dados sempre que o nome do servidor for alterado.</span><span class="sxs-lookup"><span data-stu-id="da6d2-114">If you are using a remote server, or if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is configured using the server name, you must update the database connection information whenever the server name is changed.</span></span>  
  
## <a name="renaming-a-report-server-computer"></a><span data-ttu-id="da6d2-115">Renomeando um computador de servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="da6d2-115">Renaming a Report Server Computer</span></span>  
 <span data-ttu-id="da6d2-116">Se você renomear um computador que executa um servidor de relatório, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="da6d2-116">If you rename a computer that runs a report server, do the following:</span></span>  
  
1.  <span data-ttu-id="da6d2-117">Abra **RSReportServer.config** em um editor de texto e modifique a `UrlRoot` configuração para refletir o novo nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="da6d2-117">Open **RSReportServer.config** in a text editor and modify the `UrlRoot` setting to reflect the new server name.</span></span> <span data-ttu-id="da6d2-118">A configuração `UrlRoot` é usada pelas extensões de entrega para compor o URL usado para acessar itens armazenados no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="da6d2-118">The `UrlRoot` setting is used by delivery extensions to compose the URL used to access items stored on the report server.</span></span> <span data-ttu-id="da6d2-119">A alteração do endereço URL do servidor de relatório requer a atualização da configuração `UrlRoot` para que as assinaturas continuem a entregar os relatórios conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="da6d2-119">Changing the report server URL address requires that you update the `UrlRoot` setting so that subscriptions continue to deliver reports as expected.</span></span>  
  
2.  <span data-ttu-id="da6d2-120">No mesmo arquivo, se estiver definida, modifique a configuração `ReportServerUrl` para refletir o novo nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="da6d2-120">In the same file, if it is set, modify the `ReportServerUrl` setting to reflect the new server name.</span></span> <span data-ttu-id="da6d2-121">Esta configuração não é usada em todas as instalações.</span><span class="sxs-lookup"><span data-stu-id="da6d2-121">Note that this setting is not used in every installation.</span></span> <span data-ttu-id="da6d2-122">Se estiver vazio, não faça nada.</span><span class="sxs-lookup"><span data-stu-id="da6d2-122">If it is empty, do nothing.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da6d2-123">Se estiver usando o WINS (Windows Internet Naming Service) na rede corporativa, o servidor de relatório e o Gerenciador de Relatórios podem continuar disponíveis com o nome anterior por um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="da6d2-123">If you are using Windows Internet Naming Service (WINS) on your corporate network, the report server and Report Manager may continue to be available under the previous name for a period of time.</span></span> <span data-ttu-id="da6d2-124">O WINS mapeia um endereço IP para cada computador ao qual oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="da6d2-124">WINS maps an IP address to each computer it services.</span></span> <span data-ttu-id="da6d2-125">Quando o WINS atualiza o endereço IP do computador renomeado, o nome antigo do computador não pode ser mais usado para acessar um servidor de relatório ou Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="da6d2-125">After WINS refreshes the IP address for the renamed computer, the old computer name can no longer be used to access a report server or Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da6d2-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da6d2-126">See Also</span></span>  
 <span data-ttu-id="da6d2-127">[Arquivo de configuração RSReportServer](rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="da6d2-127">[RSReportServer Configuration File](rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="da6d2-128">[Reporting Services Configuration Manager &#40;Modo Nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="da6d2-128">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="da6d2-129">[Servidor de relatório do Reporting Services &#40;Modo Nativo&#41;](reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="da6d2-129">[Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="da6d2-130">[Iniciar e parar o serviço Servidor de Relatório](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="da6d2-130">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 [<span data-ttu-id="da6d2-131">Utilitário rsconfig &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="da6d2-131">rsconfig Utility &#40;SSRS&#41;</span></span>](../tools/rsconfig-utility-ssrs.md)  
  
  

---
title: Caixa de diálogo Propriedades da fonte de dados, credenciais | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.credentials.f1
- "10100"
ms.assetid: 14c3eeb6-d37b-4fda-967b-43afcdb48119
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 491da16e6cd38db54c4d27bd8497ca7fdfaae5b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574550"
---
# <a name="data-source-properties-dialog-box-credentials"></a><span data-ttu-id="7e1f3-102">Caixa de diálogo Propriedades da Fonte de Dados, Credenciais</span><span class="sxs-lookup"><span data-stu-id="7e1f3-102">Data Source Properties Dialog Box, Credentials</span></span>
  <span data-ttu-id="7e1f3-103">Selecione **Credenciais** na caixa de diálogo **Propriedades da Fonte de Dados** para exibir e modificar as credenciais a fim de estabelecer conexão com a fonte de dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to a data source in the report.</span></span> <span data-ttu-id="7e1f3-104">As credenciais que você fornecer serão usadas para acessar a fonte de dados e para colocar em cache uma cópia dos dados para a visualização dos relatórios.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-104">The credentials that you provide are used to access the data source and to cache a copy of the data for previewing reports.</span></span> <span data-ttu-id="7e1f3-105">Para obter mais informações sobre como os dados de visualização são armazenados em cache, consulte [Visualizando relatórios](reports/previewing-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7e1f3-105">For more information about how preview data is cached, see [Previewing Reports](reports/previewing-reports.md).</span></span> <span data-ttu-id="7e1f3-106">Para obter mais informações sobre credenciais, consulte [Especificar informações de credenciais e de conexão para fontes de dados de relatório](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="7e1f3-106">For more information about credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7e1f3-107">Opções</span><span class="sxs-lookup"><span data-stu-id="7e1f3-107">Options</span></span>  
 <span data-ttu-id="7e1f3-108">**Usar a Autenticação do Windows (segurança integrada)**</span><span class="sxs-lookup"><span data-stu-id="7e1f3-108">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="7e1f3-109">Selecione esta opção para usar a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-109">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="7e1f3-110">**Usar este nome de usuário e senha**</span><span class="sxs-lookup"><span data-stu-id="7e1f3-110">**Use this user name and password**</span></span>  
 <span data-ttu-id="7e1f3-111">Selecione esta opção para fornecer um nome de usuário e senha específicos.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-111">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="7e1f3-112">Em fontes de dados compartilhadas: quando você publica o projeto do servidor de relatórios no servidor de destino, o nome de usuário e a senha são salvos como as credenciais armazenadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-112">For shared data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="7e1f3-113">Se você quiser usar o nome de usuário e a senha como credenciais do Windows, poderá editar as propriedades da fonte de dados compartilhada no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-113">If you want to use the user name and password as Windows credentials, you can edit the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="7e1f3-114">Para obter mais informações, consulte [Criar, excluir ou modificar uma fonte de dados compartilhada &#40;Gerenciador de Relatórios&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7e1f3-114">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span></span>  
  
 <span data-ttu-id="7e1f3-115">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="7e1f3-115">**User name**</span></span>  
 <span data-ttu-id="7e1f3-116">Digite um nome de usuário para fazer logon na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-116">Type a user name to log in to the data source.</span></span>  
  
 <span data-ttu-id="7e1f3-117">**Senha**</span><span class="sxs-lookup"><span data-stu-id="7e1f3-117">**Password**</span></span>  
 <span data-ttu-id="7e1f3-118">Digite uma senha para fazer logon na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-118">Type a password to log in to the data source.</span></span>  
  
 <span data-ttu-id="7e1f3-119">**Solicitar credenciais**</span><span class="sxs-lookup"><span data-stu-id="7e1f3-119">**Prompt for credentials**</span></span>  
 <span data-ttu-id="7e1f3-120">Selecione esta opção para solicitar as credenciais quando o relatório for executado.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-120">Select this option to prompt for credentials when the report is run.</span></span>  
  
 <span data-ttu-id="7e1f3-121">**Informar a cadeia de caracteres da solicitação**</span><span class="sxs-lookup"><span data-stu-id="7e1f3-121">**Enter prompt string**</span></span>  
 <span data-ttu-id="7e1f3-122">Digite uma instrução para que o usuário forneça as credenciais de logon para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-122">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="7e1f3-123">**Sem credenciais**</span><span class="sxs-lookup"><span data-stu-id="7e1f3-123">**No credentials**</span></span>  
 <span data-ttu-id="7e1f3-124">Selecione esta opção para não fornecer nenhuma credencial para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-124">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="7e1f3-125">Esta opção só funcionará se a fonte de dados não aceitar credenciais ou se você estiver passando as credenciais de alguma outra forma.</span><span class="sxs-lookup"><span data-stu-id="7e1f3-125">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1f3-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e1f3-126">See Also</span></span>  
 <span data-ttu-id="7e1f3-127">[Caixa de diálogo Propriedades da fonte de dados, geral](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span><span class="sxs-lookup"><span data-stu-id="7e1f3-127">[Data Source Properties Dialog Box, General](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span></span>  
 <span data-ttu-id="7e1f3-128">[Especificar informações de credenciais e de conexão para fontes de dados de relatório](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="7e1f3-128">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 [<span data-ttu-id="7e1f3-129">Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7e1f3-129">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  

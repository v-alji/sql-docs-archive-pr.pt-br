---
title: Plano de manutenção (página Relatório e Log) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reportinglogging.f1
ms.assetid: 3a30b17a-3deb-446f-900a-62f88934a90f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c7a95a7092ce2cdac4aa0540a5cb57d86b48497
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572531"
---
# <a name="maintenance-plan-reporting-and-logging-page"></a><span data-ttu-id="00f0c-102">Plano de manutenção (página Relatório e log)</span><span class="sxs-lookup"><span data-stu-id="00f0c-102">Maintenance Plan (Reporting and Logging Page)</span></span>
  <span data-ttu-id="00f0c-103">Use a caixa de diálogo **Relatório e Log** , para configurar os relatórios e logs gerados quando os planos de manutenção são executados.</span><span class="sxs-lookup"><span data-stu-id="00f0c-103">Use the **Reporting and Logging** dialog box to configure the reports and logs that are generated when maintenance plans are executed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="00f0c-104">Opções</span><span class="sxs-lookup"><span data-stu-id="00f0c-104">Options</span></span>  
 <span data-ttu-id="00f0c-105">**Gerar um relatório de arquivo de texto**</span><span class="sxs-lookup"><span data-stu-id="00f0c-105">**Generate a text file report**</span></span>  
 <span data-ttu-id="00f0c-106">Especifique se deseja que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] grave um relatório de arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="00f0c-106">Specify if you want [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to write a text file report.</span></span>  
  
 <span data-ttu-id="00f0c-107">**Criar um novo arquivo**</span><span class="sxs-lookup"><span data-stu-id="00f0c-107">**Create a new file**</span></span>  
 <span data-ttu-id="00f0c-108">Crie um arquivo de relatório novo para cada execução do plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="00f0c-108">Create a new report file for each execution of the maintenance plan.</span></span> <span data-ttu-id="00f0c-109">Por padrão, os arquivos de relatório são gravados no computador de hospedagem da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contém esse plano de manutenção, na pasta estabelecida como a pasta de log padrão, durante a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00f0c-109">By default, the report files are written to the computer hosting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains this maintenance plan, in the folder established as the default log folder during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup.</span></span> <span data-ttu-id="00f0c-110">Para especificar uma pasta diferente, digite o caminho completo da pasta na caixa de texto **Pasta** ou, clique no botão Procurar ( **...** ), e navegue até a pasta desejada.</span><span class="sxs-lookup"><span data-stu-id="00f0c-110">To specify a different folder, enter the full path of the folder in the **Folder** text box, or click the browse button (**...**) and navigate to the desired folder.</span></span>  
  
 <span data-ttu-id="00f0c-111">**Anexar ao arquivo**</span><span class="sxs-lookup"><span data-stu-id="00f0c-111">**Append to file**</span></span>  
 <span data-ttu-id="00f0c-112">Anexe o relatório de cada plano de execução ao arquivo especificado na caixa de texto **Nome do arquivo** .</span><span class="sxs-lookup"><span data-stu-id="00f0c-112">Append the report from each plan execution to the file specified in the **File name** text box.</span></span> <span data-ttu-id="00f0c-113">Você também pode especificar um arquivo clicando no botão procurar e selecionando um arquivo na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="00f0c-113">You may also specify a file by clicking the browse button and selecting a file from the dialog box.</span></span>  
  
 <span data-ttu-id="00f0c-114">**Enviar relatório a um recipiente de e-mail**</span><span class="sxs-lookup"><span data-stu-id="00f0c-114">**Send report to an e-mail recipient**</span></span>  
 <span data-ttu-id="00f0c-115">Transmita o resultado de um plano de manutenção por e-mail.</span><span class="sxs-lookup"><span data-stu-id="00f0c-115">Transmit the outcome of a maintenance plan execution via e-mail.</span></span> <span data-ttu-id="00f0c-116">Essa opção estará disponível apenas se o Database Mail estiver habilitado e configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="00f0c-116">This option is only available if Database Mail is enabled and properly configured.</span></span>  
  
 <span data-ttu-id="00f0c-117">**Operador do agente**</span><span class="sxs-lookup"><span data-stu-id="00f0c-117">**Agent operator**</span></span>  
 <span data-ttu-id="00f0c-118">Selecione na lista um operador do agente que será o recipiente do e-mail.</span><span class="sxs-lookup"><span data-stu-id="00f0c-118">Select an agent operator from the list who will be the recipient of the e-mail.</span></span> <span data-ttu-id="00f0c-119">Essa opção está disponível somente se o mail estiver habilitado corretamente</span><span class="sxs-lookup"><span data-stu-id="00f0c-119">This option is only available if mail is enabled and properly</span></span>  
  
 <span data-ttu-id="00f0c-120">**Informações estendidas em log**</span><span class="sxs-lookup"><span data-stu-id="00f0c-120">**Log extended information**</span></span>  
 <span data-ttu-id="00f0c-121">Inclua mais informações no log.</span><span class="sxs-lookup"><span data-stu-id="00f0c-121">Include more information in the log.</span></span> <span data-ttu-id="00f0c-122">A inclusão dessa opção aumentará o tamanho do histórico de plano de manutenção armazenado.</span><span class="sxs-lookup"><span data-stu-id="00f0c-122">Including this option will increase the size of the stored maintenance plan history.</span></span>  
  
 <span data-ttu-id="00f0c-123">**Registrar no servidor remoto**</span><span class="sxs-lookup"><span data-stu-id="00f0c-123">**Log to remote server**</span></span>  
 <span data-ttu-id="00f0c-124">Registra o histórico do plano de manutenção em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="00f0c-124">Logs maintenance plan history to a remote server.</span></span>  
  
 <span data-ttu-id="00f0c-125">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="00f0c-125">**Connection**</span></span>  
 <span data-ttu-id="00f0c-126">Especifica as informações de conexão a serem usadas ao fazer logon em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="00f0c-126">Specifies the connection information to use when logging to a remote server.</span></span>  
  
 <span data-ttu-id="00f0c-127">**Novo**</span><span class="sxs-lookup"><span data-stu-id="00f0c-127">**New**</span></span>  
 <span data-ttu-id="00f0c-128">Exibe a caixa de diálogo **Propriedades da Conexão** .</span><span class="sxs-lookup"><span data-stu-id="00f0c-128">Displays the **Connection Properties** dialog box.</span></span> <span data-ttu-id="00f0c-129">Usada para configurar informações de conexão novas para fazer o logon em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="00f0c-129">Used to configure new connection information for logging to a remote server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f0c-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="00f0c-130">See Also</span></span>  
 <span data-ttu-id="00f0c-131">[Planos de manutenção](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="00f0c-131">[Maintenance Plans](maintenance-plans.md) </span></span>  
 [<span data-ttu-id="00f0c-132">Database Mail</span><span class="sxs-lookup"><span data-stu-id="00f0c-132">Database Mail</span></span>](../database-mail/database-mail.md)  
  
  

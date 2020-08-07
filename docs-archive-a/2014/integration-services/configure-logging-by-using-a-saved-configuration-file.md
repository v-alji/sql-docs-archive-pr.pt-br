---
title: Configurar o registro em log usando um arquivo de configuração salvo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], logs
- logs [Integration Services], containers
ms.assetid: e5fdbbcb-94ca-4912-aa7c-0d89cebbd308
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8eb517462d9e932906f739678fbd46c1004fb84d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575277"
---
# <a name="configure-logging-by-using-a-saved-configuration-file"></a><span data-ttu-id="62f2a-102">Configurar o log por meio de um arquivo de configuração salvo</span><span class="sxs-lookup"><span data-stu-id="62f2a-102">Configure Logging by Using a Saved Configuration File</span></span>
  <span data-ttu-id="62f2a-103">Este procedimento descreve como configurar o registro em log de novos contêineres em um pacote carregando um arquivo de configuração de registro em log salvo anteriormente.</span><span class="sxs-lookup"><span data-stu-id="62f2a-103">This procedure describes how to configure logging for new containers in a package by loading a previously saved logging configuration file.</span></span>  
  
 <span data-ttu-id="62f2a-104">Por padrão, todos os contêineres em um pacote usam a mesma configuração de registro que o seu contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="62f2a-104">By default, all containers in a package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="62f2a-105">Por exemplo, as tarefas em um Loop Foreach usam a mesma configuração de registro que o Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="62f2a-105">For example, the tasks in a Foreach Loop use the same logging configuration as the Foreach Loop.</span></span>  
  
### <a name="to-configure-logging-for-a-container"></a><span data-ttu-id="62f2a-106">Para configurar o registro de um contêiner</span><span class="sxs-lookup"><span data-stu-id="62f2a-106">To configure logging for a container</span></span>  
  
1.  <span data-ttu-id="62f2a-107">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="62f2a-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="62f2a-108">No menu **SSIS** , clique em **Registrar em Log**.</span><span class="sxs-lookup"><span data-stu-id="62f2a-108">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="62f2a-109">Expanda a exibição de árvore do pacote e selecione o contêiner a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="62f2a-109">Expand the package tree view and select the container to configure.</span></span>  
  
4.  <span data-ttu-id="62f2a-110">Na guia **Provedores e Logs** , selecione os logs a serem usados no contêiner.</span><span class="sxs-lookup"><span data-stu-id="62f2a-110">On the **Providers and Logs** tab, select the logs to use for the container.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62f2a-111">Você só pode criar logs no nível de pacote.</span><span class="sxs-lookup"><span data-stu-id="62f2a-111">You can create logs only at the package level.</span></span> <span data-ttu-id="62f2a-112">Para obter mais informações, consulte [Habilitar o log de pacote no SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="62f2a-112">For more information, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
5.  <span data-ttu-id="62f2a-113">Clique na guia **Detalhes** e clique em **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="62f2a-113">Click the **Details** tab and click **Load**.</span></span>  
  
6.  <span data-ttu-id="62f2a-114">Localize o arquivo de configuração de registro que você deseja usar e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="62f2a-114">Locate the logging configuration file you want to use and click **Open**.</span></span>  
  
7.  <span data-ttu-id="62f2a-115">Opcionalmente, selecione uma entrada de log diferente para o log marcando sua caixa de seleção na coluna **Eventos** .</span><span class="sxs-lookup"><span data-stu-id="62f2a-115">Optionally, select a different log entry to log by selecting its check box in the **Events** column.</span></span> <span data-ttu-id="62f2a-116">Clique em **Avançado** para selecionar o tipo de informações a serem registradas nesta entrada.</span><span class="sxs-lookup"><span data-stu-id="62f2a-116">Click **Advanced** to select the type of information to log for this entry.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62f2a-117">O novo contêiner pode incluir entradas de log adicionais que não estão disponíveis para o contêiner usado originalmente para criar a configuração de registro.</span><span class="sxs-lookup"><span data-stu-id="62f2a-117">The new container may include additional log entries that are not available for the container originally used to create the logging configuration.</span></span> <span data-ttu-id="62f2a-118">Essas entradas de log adicionais devem ser selecionadas manualmente se você quiser que elas sejam registradas.</span><span class="sxs-lookup"><span data-stu-id="62f2a-118">These additional log entries must be selected manually if you want them to be logged.</span></span>  
  
8.  <span data-ttu-id="62f2a-119">Para salvar a versão atualizada da configuração de registro, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="62f2a-119">To save the updated version of the logging configuration, click **Save**.</span></span>  
  
9. <span data-ttu-id="62f2a-120">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="62f2a-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f2a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="62f2a-121">See Also</span></span>  
 [<span data-ttu-id="62f2a-122">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="62f2a-122">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  

---
title: Habilitar log de pacote no SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], enabling
ms.assetid: b69a8593-5bb0-4f04-87d2-f8e7bd7eb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d73dbca034047e853669dd503a62e105d1dd7b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574817"
---
# <a name="enable-package-logging-in-sql-server-data-tools"></a><span data-ttu-id="9b925-102">Habilitar o log de pacote no SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="9b925-102">Enable Package Logging in SQL Server Data Tools</span></span>
  <span data-ttu-id="9b925-103">Este procedimento descreve como adicionar registros a um pacote, configurar os registros no nível do pacote e salvar a configuração dos registros em um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="9b925-103">This procedure describes how to add logs to a package, configure package-level logging, and save the logging configuration to an XML file.</span></span> <span data-ttu-id="9b925-104">Você só pode adicionar os registros no nível do pacote, mas o pacote não precisa executar os registros para habilitar os registros nos contêineres incluídos no pacote.</span><span class="sxs-lookup"><span data-stu-id="9b925-104">You can add logs only at the package level, but the package does not have to perform logging to enable logging in the containers that the package includes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9b925-105">Se você implantar o projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , o nível de log definido para a execução do pacote substituirá o log do pacote configurado usando o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b925-105">If you deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the logging level that you set for the package execution overrides the package logging that you configure using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9b925-106">Por padrão, os contêineres de um pacote usam a mesma configuração de registro que o seu contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="9b925-106">By default, the containers in the package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="9b925-107">Para obter informações sobre como definir opções de log para contêineres individuais, consulte [Configurar o registro em log por meio de um arquivo de configuração salvo](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="9b925-107">For information about setting logging options for individual containers, see [Configure Logging by Using a Saved Configuration File](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span></span>  
  
### <a name="to-enable-logging-in-a-package"></a><span data-ttu-id="9b925-108">Para habilitar registros em um pacote</span><span class="sxs-lookup"><span data-stu-id="9b925-108">To enable logging in a package</span></span>  
  
1.  <span data-ttu-id="9b925-109">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="9b925-109">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9b925-110">No menu **SSIS** , clique em **Registrar em Log**.</span><span class="sxs-lookup"><span data-stu-id="9b925-110">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="9b925-111">Selecione um provedor de log na lista **Tipo de provedor** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9b925-111">Select a log provider in the **Provider type** list, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="9b925-112">Na coluna **Configuração**, selecione um gerenciador de conexões ou clique em **\<New connection>** para criar um gerenciador de conexões do tipo apropriado para o provedor de logs.</span><span class="sxs-lookup"><span data-stu-id="9b925-112">In the **Configuration** column, select a connection manager or click **\<New connection>** to create a new connection manager of the appropriate type for the log provider.</span></span> <span data-ttu-id="9b925-113">Dependendo do provedor selecionado, use um dos seguintes gerenciadores de conexões:</span><span class="sxs-lookup"><span data-stu-id="9b925-113">Depending on the selected provider, use one of the following connection managers:</span></span>  
  
    -   <span data-ttu-id="9b925-114">Para arquivos de texto, use um gerenciador de conexões de Arquivo.</span><span class="sxs-lookup"><span data-stu-id="9b925-114">For Text files, use a File connection manager.</span></span> <span data-ttu-id="9b925-115">Para saber mais, veja [File Connection Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="9b925-115">For more information, see [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
    -   <span data-ttu-id="9b925-116">Para o [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use um Gerenciador de conexões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="9b925-116">For [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use a File connection manager.</span></span>  
  
    -   <span data-ttu-id="9b925-117">Para o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use um gerenciador de conexões OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9b925-117">For [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use an OLE DB connection manager.</span></span> <span data-ttu-id="9b925-118">Para obter mais informações, consulte [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9b925-118">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
    -   <span data-ttu-id="9b925-119">Para o Log de Eventos de Windows, não faça nada.</span><span class="sxs-lookup"><span data-stu-id="9b925-119">For Windows Event Log, do nothing.</span></span> [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="9b925-120">cria o log automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9b925-120">automatically creates the log.</span></span>  
  
    -   <span data-ttu-id="9b925-121">Para arquivos XML, use um gerenciador de conexões de Arquivo.</span><span class="sxs-lookup"><span data-stu-id="9b925-121">For XML files, use a File connection manager.</span></span>  
  
5.  <span data-ttu-id="9b925-122">Repita as etapas 3 e 4 para cada log a ser usado no pacote.</span><span class="sxs-lookup"><span data-stu-id="9b925-122">Repeat steps 3 and 4 for each log to use in the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b925-123">Um pacote pode utilizar mais de um log de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="9b925-123">A package can use more than one log of each type.</span></span>  
  
6.  <span data-ttu-id="9b925-124">Opcionalmente, marque a caixa de seleção no nível de pacote, selecione os logs a serem atualizados no registro no nível do pacote e clique na guia **Detalhes** .</span><span class="sxs-lookup"><span data-stu-id="9b925-124">Optionally, select the package-level check box, select the logs to use for package-level logging, and then click the **Details** tab.</span></span>  
  
7.  <span data-ttu-id="9b925-125">Na guia **Detalhes** , selecione **Eventos** para registrar todas as entradas de log ou desmarque **Eventos** para selecionar eventos individuais.</span><span class="sxs-lookup"><span data-stu-id="9b925-125">On the **Details** tab, select **Events** to log all log entries, or clear **Events** to select individual events.</span></span>  
  
8.  <span data-ttu-id="9b925-126">Opcionalmente, clique em **Avançado** para especificar quais informações registrar.</span><span class="sxs-lookup"><span data-stu-id="9b925-126">Optionally, click **Advanced** to specify which information to log.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b925-127">Por padrão, todas informações são registradas.</span><span class="sxs-lookup"><span data-stu-id="9b925-127">By default, all information is logged.</span></span>  
  
9. <span data-ttu-id="9b925-128">Na guia **Detalhes** , clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="9b925-128">On the **Details** tab, click **Save.**</span></span> <span data-ttu-id="9b925-129">A caixa de diálogo **Salvar como** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9b925-129">The **Save As** dialog box appears.</span></span> <span data-ttu-id="9b925-130">Localize a pasta em que deseja salvar as configurações de registro, digite um nome de arquivo para as novas configurações de log e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9b925-130">Locate the folder in which to save the logging configuration, type a file name for the new log configuration, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="9b925-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b925-131">Click **OK**.</span></span>  
  
11. <span data-ttu-id="9b925-132">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="9b925-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b925-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b925-133">See Also</span></span>  
 <span data-ttu-id="9b925-134">[Log de&#41; Integration Services &#40;SSIS](performance/integration-services-ssis-logging.md) </span><span class="sxs-lookup"><span data-stu-id="9b925-134">[Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md) </span></span>  
 [<span data-ttu-id="9b925-135">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b925-135">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  

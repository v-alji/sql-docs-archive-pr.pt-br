---
title: Configurar pontos de verificação para reiniciar um pacote com falha | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- checkpoints [Integration Services]
- restarting packages
- starting packages
ms.assetid: 9afffa5a-d803-4653-8afc-386453fc163f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a85354377453e0b24692ab8c2b567cc8998b6b05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683641"
---
# <a name="configure-checkpoints-for-restarting-a-failed-package"></a><span data-ttu-id="39e95-102">Configurar pontos de verificação para reinicializar um pacote com falha</span><span class="sxs-lookup"><span data-stu-id="39e95-102">Configure Checkpoints for Restarting a Failed Package</span></span>
  <span data-ttu-id="39e95-103">Você pode configurar os pacotes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para reiniciá-los a partir de um ponto de falha em vez de executar novamente todo o pacote, selecionando as propriedades que se aplicam aos pontos de verificação.</span><span class="sxs-lookup"><span data-stu-id="39e95-103">You configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to restart from a point of failure, instead of rerunning the entire package, by setting the properties that apply to checkpoints.</span></span>  
  
### <a name="to-configure-a-package-to-restart"></a><span data-ttu-id="39e95-104">Para configurar um pacote para reinicialização</span><span class="sxs-lookup"><span data-stu-id="39e95-104">To configure a package to restart</span></span>  
  
1.  <span data-ttu-id="39e95-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="39e95-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure.</span></span>  
  
2.  <span data-ttu-id="39e95-106">No **Gerenciador de Soluções**, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="39e95-106">In **Solution Explorer**, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="39e95-107">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="39e95-107">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="39e95-108">Clique com o botão direito do mouse em qualquer lugar da tela de fundo da superfície de design do fluxo de controle e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="39e95-108">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="39e95-109">Defina a Propriedade SaveCheckpoints como `True` .</span><span class="sxs-lookup"><span data-stu-id="39e95-109">Set the SaveCheckpoints property to `True`.</span></span>  
  
6.  <span data-ttu-id="39e95-110">Digite o nome do arquivo de ponto de verificação na propriedade CheckpointFileName.</span><span class="sxs-lookup"><span data-stu-id="39e95-110">Type the name of the checkpoint file in the CheckpointFileName property.</span></span>  
  
7.  <span data-ttu-id="39e95-111">Defina a propriedade CheckpointUsage como um dos dois valores:</span><span class="sxs-lookup"><span data-stu-id="39e95-111">Set the CheckpointUsage property to one of two values:</span></span>  
  
    -   <span data-ttu-id="39e95-112">Selecione `Always` para reiniciar o pacote partindo sempre de um ponto de verificação.</span><span class="sxs-lookup"><span data-stu-id="39e95-112">Select `Always` to always restart the package from the checkpoint.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="39e95-113">Um erro ocorrerá se o arquivo do ponto de verificação não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="39e95-113">An error occurs if the checkpoint file is not available.</span></span>  
  
    -   <span data-ttu-id="39e95-114">Selecione `IfExists` para reiniciar o pacote apenas se o arquivo de ponto de verificação estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="39e95-114">Select `IfExists` to restart the package only if the checkpoint file is available.</span></span>  
  
8.  <span data-ttu-id="39e95-115">Configure as tarefas e os contêineres a partir dos quais o pacote pode ser reiniciado.</span><span class="sxs-lookup"><span data-stu-id="39e95-115">Configure the tasks and containers from which the package can restart.</span></span>  
  
    -   <span data-ttu-id="39e95-116">Clique com o botão direito do mouse em uma tarefa ou contêiner e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="39e95-116">Right-click a task or container and click **Properties**.</span></span>  
  
    -   <span data-ttu-id="39e95-117">Defina a Propriedade FailPackageOnFailure como `True` para cada tarefa e contêiner selecionados.</span><span class="sxs-lookup"><span data-stu-id="39e95-117">Set the FailPackageOnFailure property to `True` for each selected task and container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e95-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39e95-118">See Also</span></span>  
 [<span data-ttu-id="39e95-119">Reiniciar pacotes por meio de pontos de verificação</span><span class="sxs-lookup"><span data-stu-id="39e95-119">Restart Packages by Using Checkpoints</span></span>](packages/restart-packages-by-using-checkpoints.md)  
  
  

---
title: Executar o aplicativo Data Quality Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.browseforservers.f1
- sql12.dqs.connecttoserver.f1
ms.assetid: 0b2aa202-7ab2-4c9d-b0f1-802588053a1e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45372ce22fd1b18f0ec13f7a7fd76a369b78dfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685951"
---
# <a name="run-the-data-quality-client-application"></a><span data-ttu-id="28b9b-102">Executar o aplicativo do cliente do Data Quality</span><span class="sxs-lookup"><span data-stu-id="28b9b-102">Run the Data Quality Client Application</span></span>
  <span data-ttu-id="28b9b-103">É possível usar o [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) executando o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] e fazendo logon em um [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28b9b-103">You can use [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) by running [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and logging on to a [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="28b9b-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="28b9b-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="28b9b-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="28b9b-105">Prerequisites</span></span>  
 <span data-ttu-id="28b9b-106">Você precisa ter concluído a instalação do [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] executando o arquivo DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="28b9b-106">You must have completed the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="28b9b-107">Para obter mais informações, consulte [Executar o DQSInstaller.exe para concluir a instalação do Data Quality Server](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="28b9b-107">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="28b9b-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="28b9b-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="28b9b-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="28b9b-109">Permissions</span></span>  
 <span data-ttu-id="28b9b-110">Você deve ter uma das três funções DQS (dqs_adminstrator, dqs_kb_editor ou dqs_kb_operator) concedidas no banco de dados DQS_MAIN para que possa fazer logon no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28b9b-110">You must have one of the three DQS roles (dqs_adminstrator, dqs_kb_editor, or dqs_kb_operator) granted on the DQS_MAIN database to be able to log on to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="run-data-quality-client"></a><a name="Run"></a><span data-ttu-id="28b9b-111">Executar Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="28b9b-111">Run Data Quality Client</span></span>  
 <span data-ttu-id="28b9b-112">Para executar o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] no computador onde ele foi instalado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="28b9b-112">To run [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] on the computer where you have installed it, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="28b9b-113">Clique em **Iniciar**, aponte para **Todos os Programas**, clique em **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, clique em **Data Quality Services**e clique em **Cliente Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="28b9b-113">Click **Start**, point to **All Programs**, click **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="28b9b-114">Na caixa de diálogo **Conectar ao Servidor**:</span><span class="sxs-lookup"><span data-stu-id="28b9b-114">In the **Connect to Server** dialog box:</span></span>  
  
    1.  <span data-ttu-id="28b9b-115">Especifique o servidor ao qual você deseja conectar o aplicativo [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28b9b-115">Specify the server that you want to connect the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application to.</span></span> <span data-ttu-id="28b9b-116">Selecione **(LOCAL)** para conectar ao [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="28b9b-116">Select **(LOCAL)** to connect to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] on the local computer.</span></span> <span data-ttu-id="28b9b-117">Você também pode clicar na seta para baixo e selecionar **\<Browse network for more servers>** para se conectar a um servidor diferente (ou para se conectar ao servidor local por nome).</span><span class="sxs-lookup"><span data-stu-id="28b9b-117">You can also click the down arrow and select **\<Browse network for more servers>** to connect to a different server (or to connect to the local server by name).</span></span> <span data-ttu-id="28b9b-118">A caixa de diálogo **Procurar Servidores** será exibida.</span><span class="sxs-lookup"><span data-stu-id="28b9b-118">The **Browse for Servers** dialog box will be displayed.</span></span> <span data-ttu-id="28b9b-119">Você pode selecionar um servidor na guia **Servidores Locais** ou na guia **Servidores de Rede** .</span><span class="sxs-lookup"><span data-stu-id="28b9b-119">You can select a server in the **Local Servers** tab or in the **Network Servers** tab.</span></span>  
  
    2.  <span data-ttu-id="28b9b-120">Se você deseja criptografar a transferência de dados entre o [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] e o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], clique em **Opções** e marque a caixa de seleção **Criptografar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="28b9b-120">If you want to encrypt data transfer between [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], click **Options**, and then select the **Encrypt Connection** check box.</span></span>  
  
3.  <span data-ttu-id="28b9b-121">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="28b9b-121">Click **Connect**.</span></span>  
  
 <span data-ttu-id="28b9b-122">A tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] é exibida.</span><span class="sxs-lookup"><span data-stu-id="28b9b-122">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen appears.</span></span> <span data-ttu-id="28b9b-123">Para obter mais informações, consulte [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-client-home-screen.md).</span><span class="sxs-lookup"><span data-stu-id="28b9b-123">For more information, see [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md).</span></span>  
  
  

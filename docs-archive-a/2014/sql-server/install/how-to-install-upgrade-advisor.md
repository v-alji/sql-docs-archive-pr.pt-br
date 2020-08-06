---
title: Como instalar o supervisor de atualização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, installing
- Upgrade Advisor [SQL Server], installing
ms.assetid: 481b0704-ce79-4543-b141-67306128aa2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3ed5b66522126bfabc94bfa8036ec6c31ac04500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582792"
---
# <a name="how-to-install-upgrade-advisor"></a><span data-ttu-id="4f3b1-102">Como fazer: Para instalar o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="4f3b1-102">How to: Install Upgrade Advisor</span></span>
  <span data-ttu-id="4f3b1-103">O Supervisor de Atualização dá suporte à análise remota de todos os componentes com suporte, exceto o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f3b1-103">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="4f3b1-104">Se você não estiver verificando instâncias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você pode instalar o Supervisor de Atualização em qualquer computador que pode se conectar às suas instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f3b1-104">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4f3b1-105">O computador também deve atender aos pré-requisitos do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-105">The computer must also meet Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="4f3b1-106">Se você estiver verificando instâncias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], será necessário instalar o Supervisor de Atualização no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="4f3b1-107">Para obter mais informações, consulte [instalando o supervisor de atualização](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="4f3b1-107">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
### <a name="to-install-upgrade-advisor"></a><span data-ttu-id="4f3b1-108">Para instalar o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="4f3b1-108">To install Upgrade Advisor</span></span>  
  
1.  <span data-ttu-id="4f3b1-109">Inicie a instalação usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="4f3b1-109">Start the installation using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="4f3b1-110">Se você estiver instalando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] site, clique no link **baixar** e, em seguida, clique no botão **executar** para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-110">If you are installing from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Web site, click the **Download** link and then click the **Run** button to start the installation.</span></span>  
  
    -   <span data-ttu-id="4f3b1-111">Se você estiver instalando a partir da mídia do produto, abra a pasta **Redist** , abra a pasta **supervisor de atualização** e clique duas vezes em **SQLUA.msi**.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-111">If you are installing from the product media, open the **redist** folder, open the **Upgrade Advisor** folder, and then double-click **SQLUA.msi**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f3b1-112">O Supervisor de Atualização requer o [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-112">Upgrade Advisor requires the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span></span> <span data-ttu-id="4f3b1-113">Caso ele não esteja instalado ou você tenha uma versão de pré-lançamento, aparecerá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-113">If it is not installed, or if you have a pre-release version, an error message will appear.</span></span> <span data-ttu-id="4f3b1-114">Desinstale qualquer versão anterior do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] e depois instale a versão mais recente do .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-114">Uninstall any earlier version of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] and then install the latest version of .NET Framework 4.</span></span>  
    >   
    >  <span data-ttu-id="4f3b1-115">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom é um pré-requisito para instalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supervisor de atualização e não é instalado pela instalação do supervisor de atualização.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-115">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="4f3b1-116">A instalação exige que você baixe e instale o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-116">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
2.  <span data-ttu-id="4f3b1-117">Na página **Bem-vindo à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instalação do supervisor de atualização** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-117">On the **Welcome to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor Setup** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="4f3b1-118">Na página **contrato de licença** , leia o contrato de licença.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-118">On the **License Agreement** page, read the license agreement.</span></span> <span data-ttu-id="4f3b1-119">Se você concordar, selecione **aceito o contrato de licença** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-119">If you agree, select **I accept the license agreement** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="4f3b1-120">Na página **informações de registro** , insira seu nome e empresa.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-120">On the **Registration Information** page, enter your name and company.</span></span>  
  
5.  <span data-ttu-id="4f3b1-121">Na página **seleção de recursos** , examine o valor do **caminho de instalação** .</span><span class="sxs-lookup"><span data-stu-id="4f3b1-121">On the **Feature Selection** page, review the **Installation path** value.</span></span> <span data-ttu-id="4f3b1-122">Se necessário, use o botão **procurar** para alterar o local.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-122">If necessary, use the **Browse** button to change the location.</span></span> <span data-ttu-id="4f3b1-123">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-123">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="4f3b1-124">Na página **pronto para instalar o programa** , clique em **instalar** para instalar o supervisor de atualização.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-124">On the **Ready to Install the Program** page, click **Install** to install Upgrade Advisor.</span></span>  
  
7.  <span data-ttu-id="4f3b1-125">Clique em **Concluir** para sair do assistente.</span><span class="sxs-lookup"><span data-stu-id="4f3b1-125">Click **Finish** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f3b1-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f3b1-126">See Also</span></span>  
 [<span data-ttu-id="4f3b1-127">Pré-requisitos do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="4f3b1-127">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  

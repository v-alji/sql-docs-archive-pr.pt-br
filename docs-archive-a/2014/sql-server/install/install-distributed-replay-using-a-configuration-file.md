---
title: Instalar Distributed Replay usando um arquivo de configuração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3259232c-6963-4c9c-9d10-ae42aa262eef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7757cce29c2e6b3ce4f1e91fc97cbf8be02ae521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683330"
---
# <a name="install-distributed-replay-using-a-configuration-file"></a><span data-ttu-id="16550-102">Instalar o Distributed Replay usando um arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="16550-102">Install Distributed Replay Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="16550-103">fornece a capacidade de gerar um arquivo de configuração baseado na entrada do usuário e nos padrões do sistema.</span><span class="sxs-lookup"><span data-stu-id="16550-103">Setup provides the ability to generate a configuration file based on user input and system defaults.</span></span> <span data-ttu-id="16550-104">Se você especificar que deseja instalar as ferramentas de Gerenciamento, poderá usar o arquivo de configuração para implantar os três componentes de Distributed Replay (Ferramenta de Administração, Distributed Replay Controller e Distributed Replay Client).</span><span class="sxs-lookup"><span data-stu-id="16550-104">If you specify that you want the Management tools installed, you can use the configuration file to deploy the three Distributed Replay components (administration tool, Distributed Replay controller, and the Distributed Replay client).</span></span> <span data-ttu-id="16550-105">Há suporte para a Instalação, reparo e desinstalação dos componentes do Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="16550-105">It supports Installing, repairing, and uninstalling of the Distributed Replay components.</span></span>  
  
 <span data-ttu-id="16550-106">A Instalação dá suporte ao uso do arquivo de configuração apenas por meio da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="16550-106">Setup supports the use of the configuration file only through the command-line.</span></span> <span data-ttu-id="16550-107">A ordem de processamento dos parâmetros ao usar o arquivo de configuração é descrita a seguir:</span><span class="sxs-lookup"><span data-stu-id="16550-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="16550-108">O arquivo de configuração substitui os padrões em um pacote</span><span class="sxs-lookup"><span data-stu-id="16550-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="16550-109">Os valores da linha de comando substituem os valores do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="16550-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="16550-110">Para obter mais informações sobre como usar um arquivo de configuração, consulte [instalar SQL Server 2014 usando um arquivo de configuração](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="16550-110">For more information about how to use a configuration file, see [Install SQL Server 2014 Using a Configuration File](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="16550-111">Depois de instalar o Distributed Replay, crie regras de firewall no controlador e nos computadores cliente e conceda permissões a cada computador cliente no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="16550-111">After you install Distributed Replay you must create firewall rules on the controller and client computers, and grant each client computer permissions on the target server.</span></span> <span data-ttu-id="16550-112">Para obter mais informações, veja [Concluir as etapas de pós-instalação](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span><span class="sxs-lookup"><span data-stu-id="16550-112">For more information, see [Complete the Post-Installation Steps](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span></span>  
  
### <a name="to-generate-a-configuration-file"></a><span data-ttu-id="16550-113">Para gerar um arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="16550-113">To generate a configuration file</span></span>  
  
1.  <span data-ttu-id="16550-114">Siga o Assistente de Instalação até a página **Pronto para Instalar** .</span><span class="sxs-lookup"><span data-stu-id="16550-114">Follow the Setup wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="16550-115">O caminho para o arquivo de configuração é especificado na página **Pronto para Instalar** na seção do caminho do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="16550-115">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span>  
  
2.  <span data-ttu-id="16550-116">Cancele a instalação sem realmente concluí-la para gerar o arquivo INI.</span><span class="sxs-lookup"><span data-stu-id="16550-116">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
### <a name="to-install-distributed-replay-using-the-configuration-file"></a><span data-ttu-id="16550-117">Para instalar o Distributed Replay usando o arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="16550-117">To Install Distributed Replay Using the Configuration File</span></span>  
  
-   <span data-ttu-id="16550-118">Execute a instalação no prompt de comando e forneça o ConfigurationFile.ini por meio do parâmetro ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="16550-118">Run the installation through the command prompt and supply the ConfigurationFile.ini using the ConfigurationFile parameter.</span></span>  
  
 <span data-ttu-id="16550-119">**Sintaxe de exemplo**</span><span class="sxs-lookup"><span data-stu-id="16550-119">**Sample Syntax**</span></span>  
  
 <span data-ttu-id="16550-120">O seguinte é um exemplo de como especificar o arquivo de configuração no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="16550-120">Following is an example on how to specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /CTLRSVCPASSWORD="ctlrsvcpswd" /CLTSVCPASSWORD="cltsvcpswd" / ConfigurationFile=ConfigurationFile.INI\  
```  
  
> [!NOTE]  
>  <span data-ttu-id="16550-121">Você deve especificar as duas senhas na linha de comando, porque não é possível configurá-las no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="16550-121">You must specify both passwords in the command line because you cannot configure them in the configuration file.</span></span>  
  
  

---
title: Acesso a arquivos usados por pacotes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- packages [Integration Services], security
- configuration files [Integration Services]
- checkpoint files
- Integration Services packages, security
- logs [Integration Services], security
- files [Integration Services], security
- SQL Server Integration Services packages, security
ms.assetid: 2e3ddea9-5289-4289-a70e-11c018f34977
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db9511c91c9f229b7002f5b16cf077910a4ccf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570832"
---
# <a name="access-to-files-used-by-packages"></a><span data-ttu-id="77345-102">Acesso aos arquivos usados por pacotes</span><span class="sxs-lookup"><span data-stu-id="77345-102">Access to Files Used by Packages</span></span>
  <span data-ttu-id="77345-103">O nível de proteção do pacote não protege arquivos armazenados fora do pacote.</span><span class="sxs-lookup"><span data-stu-id="77345-103">The package protection level does not protect files that are stored outside the package.</span></span> <span data-ttu-id="77345-104">Esses arquivos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="77345-104">These files include the following:</span></span>  
  
-   <span data-ttu-id="77345-105">Arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="77345-105">Configuration files</span></span>  
  
-   <span data-ttu-id="77345-106">arquivos de ponto de verificação</span><span class="sxs-lookup"><span data-stu-id="77345-106">Checkpoint files</span></span>  
  
-   <span data-ttu-id="77345-107">Arquivos de log</span><span class="sxs-lookup"><span data-stu-id="77345-107">Log files</span></span>  
  
 <span data-ttu-id="77345-108">Esses arquivos devem ser protegidos separadamente, especialmente se eles incluírem informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="77345-108">These files must be protected separately, especially if they include sensitive information.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="77345-109">Arquivos de configuração</span><span class="sxs-lookup"><span data-stu-id="77345-109">Configuration Files</span></span>  
 <span data-ttu-id="77345-110">Se você tiver informações confidenciais em uma configuração, como informações de logon e senha, deverá salvar a configuração no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ou usar uma ACL (lista de controle de acesso), para restringir acesso ao local ou à pasta na qual você armazena os arquivos e só permitir o acesso a determinadas contas.</span><span class="sxs-lookup"><span data-stu-id="77345-110">If you have sensitive information in a configuration, such as login and password information, you should consider saving the configuration to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], or use an access control list (ACL) to restrict access to the location or folder where you store the files and allow access only to certain accounts.</span></span> <span data-ttu-id="77345-111">Normalmente, você concede acesso às contas que você permite que executem pacotes, e às contas que gerenciam e solucionam problemas de pacotes, que podem incluir revisão do conteúdo de configuração, ponto de verificação e arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="77345-111">Typically, you would grant access to the accounts that you permit to run packages, and to the accounts that manage and troubleshoot packages, which may include reviewing the contents of configuration, checkpoint, and log files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="77345-112">fornece o armazenamento mais seguro porque oferece proteção nos níveis de servidor e de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="77345-112">provides the more secure storage because it offers protection at the server and database levels.</span></span> <span data-ttu-id="77345-113">Para salvar configurações no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use o tipo de configuração do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77345-113">To save configurations to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration type.</span></span> <span data-ttu-id="77345-114">Para salvar no sistema de arquivos, use o tipo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="77345-114">To save to the file system, you use the XML configuration type.</span></span>  
  
 <span data-ttu-id="77345-115">Para obter mais informações, consulte [Configurações de pacote](../../2014/integration-services/package-configurations.md), [Criar configurações de pacote](../../2014/integration-services/create-package-configurations.md)e [Considerações de segurança para uma instalação do SQL Server](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="77345-115">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md), [Create Package Configurations](../../2014/integration-services/create-package-configurations.md), and [Security Considerations for a SQL Server Installation](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span></span>  
  
## <a name="checkpoint-files"></a><span data-ttu-id="77345-116">arquivos de ponto de verificação</span><span class="sxs-lookup"><span data-stu-id="77345-116">Checkpoint Files</span></span>  
 <span data-ttu-id="77345-117">Do mesmo modo, se o arquivo de ponto de verificação usado pelo pacote incluir informações confidenciais, você deverá usar uma lista de controle de acesso (ACL) para proteger o local ou a pasta onde armazena o arquivo.</span><span class="sxs-lookup"><span data-stu-id="77345-117">Similarly, if the checkpoint file that the package uses includes sensitive information, you should use an access control list (ACL) to secure the location or folder where you store the file.</span></span> <span data-ttu-id="77345-118">Arquivos de ponto de verificação salvam informações do estado atual no andamento do pacote, bem como os valores atuais das variáveis.</span><span class="sxs-lookup"><span data-stu-id="77345-118">Checkpoint files save current state information on the progress of the package as well as the current values of variables.</span></span> <span data-ttu-id="77345-119">Por exemplo, o pacote pode incluir uma variável personalizada que contenha um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="77345-119">For example, the package may include a custom variable that contains a telephone number.</span></span> <span data-ttu-id="77345-120">Para saber mais, confira [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span><span class="sxs-lookup"><span data-stu-id="77345-120">For more information, see [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span></span>  
  
## <a name="log-files"></a><span data-ttu-id="77345-121">Arquivos de log</span><span class="sxs-lookup"><span data-stu-id="77345-121">Log Files</span></span>  
 <span data-ttu-id="77345-122">As entradas de log que são gravadas no sistema de arquivos também devem ser protegidas usando uma lista de controle de acesso (ACL).</span><span class="sxs-lookup"><span data-stu-id="77345-122">Log entries that are written to the file system should also be secured using an access control list (ACL).</span></span> <span data-ttu-id="77345-123">As entradas de log também podem ser armazenadas em tabelas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e protegidas pela segurança do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77345-123">Log entries can also be stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables and protected by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security.</span></span> <span data-ttu-id="77345-124">As entradas de logs podem incluir informações confidenciais, por exemplo, se o pacote contiver uma tarefa Executar SQL que cria uma instrução SQL referente a um número de telefone, a entrada de log para a instrução SQL incluirá o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="77345-124">Log entries may include sensitive information, For example, if the package contains an Execute SQL task that constructs an SQL statement that refers to a telephone number, the log entry for the SQL statement includes the telephone number.</span></span> <span data-ttu-id="77345-125">A instrução SQL também pode revelar informações particulares sobre nomes de tabelas e colunas nos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="77345-125">The SQL statement may also reveal private information about table and column names in databases.</span></span> <span data-ttu-id="77345-126">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="77345-126">For more information, see [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md).</span></span>  
  
  

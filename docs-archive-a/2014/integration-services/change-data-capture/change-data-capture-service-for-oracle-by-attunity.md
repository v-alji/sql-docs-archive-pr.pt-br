---
title: Serviço Change Data Capture para Oracle da Attunity | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 22ec8a5c-9550-4d38-8a4a-485ec3e53ea8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68e68e9edd91bd1d0c718b32e29c3b29f74778c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574865"
---
# <a name="change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="dde07-102">Serviço Change Data Capture para Oracle da Attunity</span><span class="sxs-lookup"><span data-stu-id="dde07-102">Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="dde07-103">O Serviço CDC para Oracle é um Serviço do Windows que examina os logs de transação do Oracle e capturam alterações a tabelas de interesse do Oracle em tabelas de alteração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dde07-103">The CDC Service for Oracle is a Windows service that scans Oracle transaction logs and captures changes to Oracle tables of interest into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] change tables.</span></span> <span data-ttu-id="dde07-104">As tabelas de alteração do SQL onde as alterações capturadas do Oracle são armazenadas são do mesmo tipo das tabelas de alteração usadas no recurso Change Data Capture nativo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dde07-104">The SQL change tables where the changes captured from Oracle are stored are the same type of change tables used in the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Change Data Capture feature.</span></span> <span data-ttu-id="dde07-105">Isto faz o consumo destas alterações tão fácil quanto consumir alterações feitas a bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dde07-105">This makes consuming these changes as easy as consuming changes made to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="dde07-106">Instalação</span><span class="sxs-lookup"><span data-stu-id="dde07-106">Installation</span></span>  
 <span data-ttu-id="dde07-107">O Serviço CDC para Oracle pode ser instalado em qualquer computador Windows com suporte com acesso a bancos de dados Oracle de origem que são capturados e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino em que reside o banco de dados de CDC de destino.</span><span class="sxs-lookup"><span data-stu-id="dde07-107">The CDC Service for Oracle can be installed on any supported Windows computer with access to the source Oracle database(s) being captured and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance where the target CDC database resides.</span></span> <span data-ttu-id="dde07-108">O Serviço CDC não precisa de uma instalação local do banco de dados Oracle ou o banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , somente seus clientes com suporte.</span><span class="sxs-lookup"><span data-stu-id="dde07-108">The CDC Service does not need a local installation of the Oracle database or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, only their supported clients.</span></span> <span data-ttu-id="dde07-109">Para obter mais informações sobre onde instalar os componentes necessários do banco de dados, consulte a seção **Pré-requisitos de banco de dados** deste tópico.</span><span class="sxs-lookup"><span data-stu-id="dde07-109">For information about where to install the required database components, see **Database Prerequisites** in this topic.</span></span>  
  
 <span data-ttu-id="dde07-110">A instalação do Serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC para Oracle coloca a interface de usuário da configuração de serviço e o programa de serviço no local selecionado.</span><span class="sxs-lookup"><span data-stu-id="dde07-110">The installation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC Service for Oracle places the service configuration UI and the service program in the selected location.</span></span> <span data-ttu-id="dde07-111">O Serviço CDC para Oracle é configurado separadamente usando o Console de Configuração do Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="dde07-111">The CDC Service for Oracle is configured separately using the Oracle CDC Service Configuration Console.</span></span> <span data-ttu-id="dde07-112">Para obter mais informações sobre como configurar o Serviço Oracle CDC, consulte [Ajuda F1 do serviço Change Data Capture para Oracle da Attunity](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="dde07-112">For more information on configuring the Oracle CDC Service, see [Change Data Capture Service for Oracle by Attunity F1 Help](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span></span>  
  
 <span data-ttu-id="dde07-113">Para instalar o serviço CDC para Oracle, execute manualmente **AttunityOracleCdcService.msi** da mídia de instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dde07-113">To install the CDC Service for Oracle, manually run **AttunityOracleCdcService.msi** from the SQL Server installation media.</span></span> <span data-ttu-id="dde07-114">Os pacotes de instalação para x86 e x64 estão localizados em \*\*.\Tools\AttunityCDCOracle \\ \*\* na mídia de instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dde07-114">Installation packages for x86 and x64 are located in **.\Tools\AttunityCDCOracle\\** on the SQL Server installation media.</span></span>  
  
 <span data-ttu-id="dde07-115">O Serviço CDC para Oracle pode ser instalado em qualquer computador Windows com suporte em que o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client esteja instalado; ele não precisa estar instalado no mesmo computador em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino está instalado.</span><span class="sxs-lookup"><span data-stu-id="dde07-115">The CDC Service for Oracle can be installed on any supported Windows computer where the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client is installed; it does not need to be installed on the same computer where the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
## <a name="supported-windows-environments"></a><span data-ttu-id="dde07-116">Ambientes de Windows com suporte</span><span class="sxs-lookup"><span data-stu-id="dde07-116">Supported Windows Environments</span></span>  
 <span data-ttu-id="dde07-117">O Serviço Change Data Capture para Oracle da Attunity pode ser executado nos ambientes de Windows a seguir:</span><span class="sxs-lookup"><span data-stu-id="dde07-117">The Change Data Capture Service for Oracle by Attunity can run in the following Windows environments:</span></span>  
  
-   <span data-ttu-id="dde07-118">Windows 8</span><span class="sxs-lookup"><span data-stu-id="dde07-118">Windows 8</span></span>  
  
-   <span data-ttu-id="dde07-119">Windows 7 de 32 bits (x86) e de 64 bits (x64)</span><span class="sxs-lookup"><span data-stu-id="dde07-119">Windows 7 32-bit (x86) and 64-bit (x64)</span></span>  
  
-   <span data-ttu-id="dde07-120">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="dde07-120">Windows Server 2012</span></span>  
  
-   <span data-ttu-id="dde07-121">Windows Server 2008 R2 com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="dde07-121">Windows Server 2008 R2 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="dde07-122">Windows Server 2008 de 32 bits (x86) e de 64 bits (x64) com Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="dde07-122">Windows Server 2008 32-bit (x86) and 64-bit (x64) with Service Pack 2</span></span>  
  
## <a name="database-prerequisites"></a><span data-ttu-id="dde07-123">Pré-requisitos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="dde07-123">Database Prerequisites</span></span>  
 <span data-ttu-id="dde07-124">Para funcionar com o Serviço CDC para Oracle, você deverá instalar o software Oracle do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="dde07-124">To work with the CDC Service for Oracle you must install the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle software.</span></span> <span data-ttu-id="dde07-125">Este é um pré-requisito que deve ser obtido do Oracle e instalado antes de instalar o Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="dde07-125">This is a prerequisite that should be obtained from Oracle and installed before installing the Oracle CDC Service.</span></span> <span data-ttu-id="dde07-126">Além disso, você precisa instalar o Cliente ODBC do SQL Server usando a Instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dde07-126">Additionally, you need to install the SQL Server ODBC Client using SQL Server Setup.</span></span>  
  
 <span data-ttu-id="dde07-127">O Serviço CDC para Oracle dá suporte às seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="dde07-127">The CDC Service for Oracle supports the following versions:</span></span>  
  
### <a name="source-oracle-database"></a><span data-ttu-id="dde07-128">Banco de dados Oracle de origem</span><span class="sxs-lookup"><span data-stu-id="dde07-128">Source Oracle Database</span></span>  
  
-   <span data-ttu-id="dde07-129">Banco de dados do Oracle 11x, qualquer versão</span><span class="sxs-lookup"><span data-stu-id="dde07-129">Oracle Database 11x, any version</span></span>  
  
-   <span data-ttu-id="dde07-130">Banco de dados do Oracle 10x, qualquer versão</span><span class="sxs-lookup"><span data-stu-id="dde07-130">Oracle Database 10x, any version</span></span>  
  
### <a name="target-sql-server-database"></a><span data-ttu-id="dde07-131">Banco de Dados do SQL Server de destino</span><span class="sxs-lookup"><span data-stu-id="dde07-131">Target SQL Server Database</span></span>  
 <span data-ttu-id="dde07-132">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="dde07-132">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="running-the-installation-program"></a><span data-ttu-id="dde07-133">Executando o programa de instalação</span><span class="sxs-lookup"><span data-stu-id="dde07-133">Running the Installation Program</span></span>  
 <span data-ttu-id="dde07-134">Para instalar o Serviço CDC para Oracle, abra o assistente de instalação para a plataforma Windows que você está usando (32/64 bits) e siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="dde07-134">To install the CDC Service for Oracle, open the installation wizard for the Windows platform you are using (32/64-bit) and follow the directions on the screen.</span></span>  
  
## <a name="uninstalling-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="dde07-135">Desinstalando o Serviço Change Data Capture para Oracle da Attunity</span><span class="sxs-lookup"><span data-stu-id="dde07-135">Uninstalling Change Data Capture Service for Oracle by Attunity</span></span>  
 <span data-ttu-id="dde07-136">É possível desinstalar o Serviço CDC para Oracle usando Painel de Controle, Programas e Recursos.</span><span class="sxs-lookup"><span data-stu-id="dde07-136">You uninstall the CDC Service for Oracle using Control Panel, Programs and Features.</span></span>  
  
 <span data-ttu-id="dde07-137">Desinstalar o Serviço CDC não exclui os bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criados.</span><span class="sxs-lookup"><span data-stu-id="dde07-137">Uninstalling the CDC Service does not delete the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases created.</span></span> <span data-ttu-id="dde07-138">Para remoção completa da ferramenta, você deverá remover o banco de dados MSXDBCDC e os bancos de dados de CDC específicos que foram criados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino com os quais você trabalhou.</span><span class="sxs-lookup"><span data-stu-id="dde07-138">For complete removal of the tool, you must remove the MSXDBCDC database and the specific CDC databases that were created in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you worked with.</span></span>  
  
 <span data-ttu-id="dde07-139">Se você desinstalar o software Serviço CDC de um computador e instalá-lo em outro, só precisará fornecer as seguintes definições:</span><span class="sxs-lookup"><span data-stu-id="dde07-139">If you uninstall the CDC Service software from one machine and install it on another computer, you only need to provide the following definitions:</span></span>  
  
-   <span data-ttu-id="dde07-140">Conta de serviço</span><span class="sxs-lookup"><span data-stu-id="dde07-140">Service account</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dde07-141">Cadeia de conexão e credenciais</span><span class="sxs-lookup"><span data-stu-id="dde07-141">connect string and credentials</span></span>  
  
-   <span data-ttu-id="dde07-142">A senha mestra</span><span class="sxs-lookup"><span data-stu-id="dde07-142">The master password</span></span>  
  
 <span data-ttu-id="dde07-143">Todas as outras definições são armazenadas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e estão disponíveis da instalação anterior em outro computador.</span><span class="sxs-lookup"><span data-stu-id="dde07-143">All the other definitions are stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and are available from the previous installation on another computer.</span></span>  
  
## <a name="in-this-documentation"></a><span data-ttu-id="dde07-144">Nesta documentação</span><span class="sxs-lookup"><span data-stu-id="dde07-144">In This Documentation</span></span>  
  
-   [<span data-ttu-id="dde07-145">Arquitetura de sistema do Serviço Change Data Capture para Oracle da Attunity</span><span class="sxs-lookup"><span data-stu-id="dde07-145">Change Data Capture Service for Oracle by Attunity System Architecture</span></span>](change-data-capture-service-for-oracle-by-attunity-system-architecture.md)  
  
-   [<span data-ttu-id="dde07-146">O Serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="dde07-146">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
-   [<span data-ttu-id="dde07-147">Ajuda F1 do Serviço Change Data Capture para Oracle da Attunity</span><span class="sxs-lookup"><span data-stu-id="dde07-147">Change Data Capture Service for Oracle by Attunity F1 Help</span></span>](change-data-capture-service-for-oracle-by-attunity-f1-help.md)  
  
-   [<span data-ttu-id="dde07-148">Guia de instruções do Serviço Change Data Capture para Oracle da Attunity</span><span class="sxs-lookup"><span data-stu-id="dde07-148">Change Data Capture Service for Oracle by Attunity How to Guide</span></span>](change-data-capture-service-for-oracle-by-attunity-how-to-guide.md)  
  
## <a name="see-also"></a><span data-ttu-id="dde07-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dde07-149">See Also</span></span>  
 [<span data-ttu-id="dde07-150">Trabalhando com o Serviço Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="dde07-150">Working with the Oracle CDC Service</span></span>](working-with-the-oracle-cdc-service.md)  
  
  

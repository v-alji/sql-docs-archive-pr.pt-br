---
title: Fazer upgrade do Data Quality Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: f396666b-7754-4efc-9507-0fd114cc32d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9d2544df341a831f2f676ec58150ed64a800fb96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572166"
---
# <a name="upgrade-data-quality-services"></a><span data-ttu-id="9f65a-102">Atualizar o Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="9f65a-102">Upgrade Data Quality Services</span></span>
  <span data-ttu-id="9f65a-103">Este tópico fornece informações sobre como atualizar sua instalação existente do Data Quality Services (DQS) para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span><span class="sxs-lookup"><span data-stu-id="9f65a-103">This topic provides information on how to upgrade your existing installation of Data Quality Services (DQS) to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span></span> <span data-ttu-id="9f65a-104">Como parte de atualizar seu Data Quality Server no DQS para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], você também deverá atualizar o esquema de bancos de dados do DQS.</span><span class="sxs-lookup"><span data-stu-id="9f65a-104">As part of upgrading your Data Quality Server in DQS to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you must also upgrade the DQS databases schema.</span></span>  
  
> [!IMPORTANT]
>  -   <span data-ttu-id="9f65a-105">Você deve fazer backup de seus bancos de dados do DQS antes de atualizar o DQS para impedir qualquer perda de dados acidental durante a atualização do esquema.</span><span class="sxs-lookup"><span data-stu-id="9f65a-105">You must back up your DQS databases before upgrading DQS to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="9f65a-106">Para obter informações sobre como fazer backup de bancos de dados DQS, veja [Fazendo backup e restaurando banco de dados do DQS](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9f65a-106">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span></span>  
> -   <span data-ttu-id="9f65a-107">Você pode se conectar à versão do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] do Data Quality Server usando a versão atual ou anterior do Cliente Data Quality ou a [Transformação de Limpeza DQS](../../integration-services/data-flow/transformations/dqs-cleansing-transformation.md) no Integration Services para executar suas tarefas de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="9f65a-107">You can connect to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] version of Data Quality Server by using the current or an earlier version of Data Quality Client or the [DQS Cleansing Transformation](../../integration-services/data-flow/transformations/dqs-cleansing-transformation.md) in Integration Services to perform your data quality tasks.</span></span>  
> -   <span data-ttu-id="9f65a-108">Você pode continuar a usar a versão do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1 do suplemento Master Data Services para Excel depois de atualizar o Data Quality Services e o Master Data Services para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span><span class="sxs-lookup"><span data-stu-id="9f65a-108">You can continue using the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1 version of Master Data Services Add-In for Excel after upgrading Data Quality Services and Master Data Services to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span></span> <span data-ttu-id="9f65a-109">No entanto, qualquer versão anterior do suplemento Master Data Services para Excel não funcionará depois de atualizar para o SQL Server 2014 CTP2.</span><span class="sxs-lookup"><span data-stu-id="9f65a-109">However, any earlier version of the Master Data Services Add-In for Excel will not work after upgrading to SQL Server 2014 CTP2.</span></span> <span data-ttu-id="9f65a-110">Você pode baixar a versão do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1 do suplemento Master Data Services para Excel [aqui](https://go.microsoft.com/fwlink/?LinkId=328664).</span><span class="sxs-lookup"><span data-stu-id="9f65a-110">You can download the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1 version of Master Data Services Add-In for Excel from [here](https://go.microsoft.com/fwlink/?LinkId=328664).</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9f65a-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9f65a-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="9f65a-112">Você deve estar conectado como um membro do grupo Administradores no computador do [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f65a-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="9f65a-113">Sua conta de usuário do Windows deve ser um membro da função de servidor fixa sysadmin na instância do SQL Server em que o [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="9f65a-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
##  <a name="upgrading-dqs"></a><a name="Upgrade"></a> <span data-ttu-id="9f65a-114">Atualizando o DQS</span><span class="sxs-lookup"><span data-stu-id="9f65a-114">Upgrading DQS</span></span>  
 <span data-ttu-id="9f65a-115">Para atualizar o DQS:</span><span class="sxs-lookup"><span data-stu-id="9f65a-115">To upgrade DQS:</span></span>  
  
1.  <span data-ttu-id="9f65a-116">Faça backup de seus bancos de dados do DQS antes de iniciar o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="9f65a-116">Back up your DQS databases before you start the upgrade process.</span></span> <span data-ttu-id="9f65a-117">Para obter informações sobre como fazer backup de bancos de dados DQS, veja [Fazendo backup e restaurando banco de dados do DQS](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9f65a-117">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="9f65a-118">Atualizar a instância do SQL Server onde o DQS está instalado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f65a-118">Upgrade the SQL Server instance where DQS is installed to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    1.  <span data-ttu-id="9f65a-119">Execute o assistente de instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f65a-119">Run the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup wizard.</span></span>  
  
    2.  <span data-ttu-id="9f65a-120">No painel esquerdo, clique em **Instalação**.</span><span class="sxs-lookup"><span data-stu-id="9f65a-120">In the left pane, click **Installation**.</span></span>  
  
    3.  <span data-ttu-id="9f65a-121">No painel direito, clique em **Atualizar do SQL Server 2005, SQL Server 2008, SQL Server 2008 R2 ou SQL Server 2012**.</span><span class="sxs-lookup"><span data-stu-id="9f65a-121">In the right pane, click **Upgrade from SQL Server 2005, SQL Server 2008, SQL Server 2008 R2 or SQL Server 2012**.</span></span>  
  
    4.  <span data-ttu-id="9f65a-122">Conclua o assistente de Instalação.</span><span class="sxs-lookup"><span data-stu-id="9f65a-122">Complete the Setup wizard.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9f65a-123">Isso atualizará a instância do SQL Server para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e também instalará o último Cliente Data Quality, caso o Cliente Data Quality tenha sido instalado anteriormente neste computador.</span><span class="sxs-lookup"><span data-stu-id="9f65a-123">This will upgrade your SQL Server instance to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and also install the latest Data Quality Client, if Data Quality Client was previously installed on this computer.</span></span> <span data-ttu-id="9f65a-124">Se você tiver o Cliente Data Quality instalado em outros computadores, execute as etapas secundárias na Etapa 2 nesses computadores para instalar a versão atual do Cliente Data Quality.</span><span class="sxs-lookup"><span data-stu-id="9f65a-124">If you have Data Quality Client installed on other computers, you must run the sub steps in Step 2 on those computers to install the current version of Data Quality Client.</span></span> <span data-ttu-id="9f65a-125">O assistente de instalação instala a versão atual do Cliente Data Quality próximo à versão existente do Cliente Data Quality.</span><span class="sxs-lookup"><span data-stu-id="9f65a-125">The Setup wizard installs the current version of Data Quality Client alongside the existing version of Data Quality Client.</span></span> <span data-ttu-id="9f65a-126">Depois de você atualizar o esquema de bancos de dados do DQS, você pode se conectar à versão do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] do Data Quality Server usando a versão atual ou anterior do Cliente Data Quality.</span><span class="sxs-lookup"><span data-stu-id="9f65a-126">After you upgrade the DQS databases schema, you can connect to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] version of Data Quality Server by using the current or an earlier version of Data Quality Client.</span></span>  
  
3.  <span data-ttu-id="9f65a-127">Atualize o esquema de banco de dados do DQS.</span><span class="sxs-lookup"><span data-stu-id="9f65a-127">Upgrade the DQS databases schema.</span></span>  
  
    1.  <span data-ttu-id="9f65a-128">Inicie o prompt de comando como administrador.</span><span class="sxs-lookup"><span data-stu-id="9f65a-128">Start Command Prompt as an administrator.</span></span>  
  
    2.  <span data-ttu-id="9f65a-129">Ao prompt de comando, altere seu diretório ao local onde DQSInstaller.exe está disponível.</span><span class="sxs-lookup"><span data-stu-id="9f65a-129">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="9f65a-130">Para a instância padrão do SQL Server, o arquivo DQSInstaller.exe estará disponível em C:\Arquivos de Programas\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span><span class="sxs-lookup"><span data-stu-id="9f65a-130">For the default instance of SQL Server, the DQSInstaller.exe file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
        ```  
        cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
        ```  
  
    3.  <span data-ttu-id="9f65a-131">No prompt de comando, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="9f65a-131">At the command prompt, type the following command, and press ENTER:</span></span>  
  
        ```  
        dqsinstaller.exe -upgrade  
        ```  
  
    4.  <span data-ttu-id="9f65a-132">O instalador solicita que você faça backup dos bancos de dados do DQS antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9f65a-132">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="9f65a-133">Se você já tiver feito backup dos bancos de dados do DQS, digite `Y` ou `Yes` e pressione ENTER para continuar com a atualização.</span><span class="sxs-lookup"><span data-stu-id="9f65a-133">If you have already backed up your DQS databases, type `Y` or `Yes`, and then press ENTER to continue with the upgrade.</span></span>  
  
    5.  <span data-ttu-id="9f65a-134">Uma mensagem de conclusão é exibida depois da atualização bem-sucedida do esquema de bancos de dados do DQS.</span><span class="sxs-lookup"><span data-stu-id="9f65a-134">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
##  <a name="verifying-the-dqs-databases-schema-upgrade"></a><a name="Verify"></a> <span data-ttu-id="9f65a-135">Verificando a atualização do esquema de banco de dados do DQS</span><span class="sxs-lookup"><span data-stu-id="9f65a-135">Verifying the DQS Databases Schema Upgrade</span></span>  
 <span data-ttu-id="9f65a-136">Para verificar se o esquema de banco de dados do DQS foi atualizado com êxito, você poderá verificar a versão atual nos bancos de dados DQS_MAIN e DQS_PROJECTS consultando a tabela A_DB_VERSION em cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f65a-136">To verify that DQS databases schema have successfully upgraded, you can check the current version in the DQS_MAIN and DQS_PROJECTS databases by querying the A_DB_VERSION table in each database.</span></span> <span data-ttu-id="9f65a-137">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="9f65a-137">To do so:</span></span>  
  
1.  <span data-ttu-id="9f65a-138">Inicie o SQL Server Management Studio e conecte-se à instância do SQL Server que contém o esquema de banco de dados do DQS atualizado.</span><span class="sxs-lookup"><span data-stu-id="9f65a-138">Start SQL Server Management Studio, and connect to the SQL Server instance that contains the upgraded DQS databases schema.</span></span>  
  
2.  <span data-ttu-id="9f65a-139">Execute a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="9f65a-139">Run the following query:</span></span>  
  
    ```  
    SELECT * FROM DQS_MAIN.dbo.A_DB_VERSION WHERE STATUS=2;  
    SELECT * FROM DQS_PROJECTS.dbo.A_DB_VERSION WHERE STATUS=2;  
    ```  
  
3.  <span data-ttu-id="9f65a-140">A saída exibirá uma entrada para cada atualização junto com a data da atualização.</span><span class="sxs-lookup"><span data-stu-id="9f65a-140">The output will display an entry for each upgrade along with the date of the upgrade.</span></span> <span data-ttu-id="9f65a-141">O VERSION_ID e ASSEMBLY_VERSION máximo na última data é a versão atual.</span><span class="sxs-lookup"><span data-stu-id="9f65a-141">The maximum VERSION_ID and ASSEMBLY_VERSION on the latest date is the current version.</span></span> <span data-ttu-id="9f65a-142">Um valor de 2 na coluna STATUS indica êxito.</span><span class="sxs-lookup"><span data-stu-id="9f65a-142">A value of 2 in the STATUS column indicates success.</span></span> <span data-ttu-id="9f65a-143">Se um erro ocorreu, o erro será listado na coluna ERROR.</span><span class="sxs-lookup"><span data-stu-id="9f65a-143">If an error has occurred, the error will be listed in the ERROR column.</span></span> <span data-ttu-id="9f65a-144">Uma saída de exemplo:</span><span class="sxs-lookup"><span data-stu-id="9f65a-144">A sample output:</span></span>  
  
    |<span data-ttu-id="9f65a-145">ID</span><span class="sxs-lookup"><span data-stu-id="9f65a-145">ID</span></span>|<span data-ttu-id="9f65a-146">UPGRADE_DATE</span><span class="sxs-lookup"><span data-stu-id="9f65a-146">UPGRADE_DATE</span></span>|<span data-ttu-id="9f65a-147">VERSION_ID</span><span class="sxs-lookup"><span data-stu-id="9f65a-147">VERSION_ID</span></span>|<span data-ttu-id="9f65a-148">ASSEMBLY_VERSION</span><span class="sxs-lookup"><span data-stu-id="9f65a-148">ASSEMBLY_VERSION</span></span>|<span data-ttu-id="9f65a-149">USER_NAME</span><span class="sxs-lookup"><span data-stu-id="9f65a-149">USER_NAME</span></span>|<span data-ttu-id="9f65a-150">STATUS</span><span class="sxs-lookup"><span data-stu-id="9f65a-150">STATUS</span></span>|<span data-ttu-id="9f65a-151">ERROR</span><span class="sxs-lookup"><span data-stu-id="9f65a-151">ERROR</span></span>|  
    |--------|-------------------|-----------------|-----------------------|----------------|------------|-----------|  
    |<span data-ttu-id="9f65a-152">1000</span><span class="sxs-lookup"><span data-stu-id="9f65a-152">1000</span></span>|<span data-ttu-id="9f65a-153">2013-08-11 05:26:39.567</span><span class="sxs-lookup"><span data-stu-id="9f65a-153">2013-08-11 05:26:39.567</span></span>|<span data-ttu-id="9f65a-154">1200</span><span class="sxs-lookup"><span data-stu-id="9f65a-154">1200</span></span>|<span data-ttu-id="9f65a-155">11.0.3000.0</span><span class="sxs-lookup"><span data-stu-id="9f65a-155">11.0.3000.0</span></span>|\<DOMAIN\UserName>|<span data-ttu-id="9f65a-156">2</span><span class="sxs-lookup"><span data-stu-id="9f65a-156">2</span></span>||  
    |<span data-ttu-id="9f65a-157">1001</span><span class="sxs-lookup"><span data-stu-id="9f65a-157">1001</span></span>|<span data-ttu-id="9f65a-158">2013-09-19 15:09:37.750</span><span class="sxs-lookup"><span data-stu-id="9f65a-158">2013-09-19 15:09:37.750</span></span>|<span data-ttu-id="9f65a-159">1600</span><span class="sxs-lookup"><span data-stu-id="9f65a-159">1600</span></span>|<span data-ttu-id="9f65a-160">12.0.xxxx.0</span><span class="sxs-lookup"><span data-stu-id="9f65a-160">12.0.xxxx.0</span></span>|\<DOMAIN\UserName>|<span data-ttu-id="9f65a-161">2</span><span class="sxs-lookup"><span data-stu-id="9f65a-161">2</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="9f65a-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f65a-162">See Also</span></span>  
 <span data-ttu-id="9f65a-163">[Instalar o Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="9f65a-163">[Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md) </span></span>  
 <span data-ttu-id="9f65a-164">[Remover objetos do Data Quality Server](../../sql-server/install/remove-data-quality-server-objects.md) </span><span class="sxs-lookup"><span data-stu-id="9f65a-164">[Remove Data Quality Server Objects](../../sql-server/install/remove-data-quality-server-objects.md) </span></span>  
 [<span data-ttu-id="9f65a-165">Atualizar para o SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="9f65a-165">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
  
  

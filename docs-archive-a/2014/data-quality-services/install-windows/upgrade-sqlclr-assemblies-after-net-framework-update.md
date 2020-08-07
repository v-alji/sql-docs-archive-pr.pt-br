---
title: Atualizar assemblies SQLCLR após atualizar o .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b1a008cc-7e6b-4655-a869-bd429f986400
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45d60db413e11828f26bd03e1c8f350645838d12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574920"
---
# <a name="upgrade-sqlclr-assemblies-after-net-framework-update"></a><span data-ttu-id="99b32-102">Atualizar assemblies SQLCLR após atualizar o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="99b32-102">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>
  [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] <span data-ttu-id="99b32-103">O DQS é uma coleção de rotinas SQLCR (SQL Common Language Runtime) que fazem referência aos assemblies do Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="99b32-103">(DQS) is a collection of SQL Common Language Runtime (SQLCR) routines that reference Microsoft .NET Framework 4 assemblies.</span></span> <span data-ttu-id="99b32-104">Quando você instala qualquer atualização do .NET Framework em seu computador que afete qualquer assembly do .NET Framework referenciado, isso leva a uma alteração na MVID (ID da Versão do Módulo) do assembly no GAC (Cache de Assembly Global).</span><span class="sxs-lookup"><span data-stu-id="99b32-104">When you install any .NET Framework updates on your computer that affect any such referenced .NET Framework assembly, it leads to a change in the Module Version ID (MVID) of the assembly in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="99b32-105">Isso causa uma incompatibilidade entre as MVIDs do assembly referenciado no GAC e o assembly no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99b32-105">This causes a mismatch between the MVIDs of the referenced assembly in GAC and the assembly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="99b32-106">Se a atualização do .NET Framework exigir que você reinicie o computador do [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , os assemblies do SQLCLR afetados serão atualizados automaticamente para corrigir o problema de incompatibilidade do MVID ao reiniciar o computador do [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99b32-106">If the .NET Framework update requires you to restart the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, the affected SQLCLR assemblies are upgraded automatically to fix the MVID mismatch issue on restarting the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span> <span data-ttu-id="99b32-107">Porém, para as atualizações do .NET Framework que não exigem que você reinicie seu computador do [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , um erro ocorre devido à incompatibilidade nos MVIDs dos assemblies quando você tenta se conectar a um [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] usando um [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="99b32-107">However, for .NET Framework updates that do not require you to restart your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, an error occurs due to the mismatch in the MVIDs of the assemblies when you try to connect to a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] using a [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span></span>  
  
```  
A new version of .NET was installed on this machine. In order to continue to work with DQS please run dqsinstaller.exe -upgradedlls.  
```  
  
 <span data-ttu-id="99b32-108">Para corrigir este problema, os assemblies SQLCLR afetados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="99b32-108">To fix this issue, the affected SQLCLR assemblies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be upgraded.</span></span> <span data-ttu-id="99b32-109">Você pode fazer isso executando o arquivo DQSInstaller.exe com o parâmetro de linha de comando **upgradedlls** para ignorar a recriação dos bancos de dados DQS e atualizar apenas os assemblies afetados.</span><span class="sxs-lookup"><span data-stu-id="99b32-109">You can do so by running the DQSInstaller.exe file with the **upgradedlls** command line parameter to skip recreating the DQS databases, and just upgrade the affected assemblies.</span></span> <span data-ttu-id="99b32-110">Isso garante que sua base de conhecimento, projetos de qualidade de dados e quaisquer outros dados no DQS sejam preservados.</span><span class="sxs-lookup"><span data-stu-id="99b32-110">This ensures that your knowledge bases, data quality projects, and any other data in DQS are preserved.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="99b32-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="99b32-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="99b32-112">Você deve estar conectado como um membro do grupo Administradores no computador do [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99b32-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="99b32-113">Sua conta de usuário do Windows deve ser um membro da função de servidor fixa sysadmin na instância do SQL Server em que o [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="99b32-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-sqlclr-assemblies"></a><span data-ttu-id="99b32-114">Para atualizar assemblies SQLCLR</span><span class="sxs-lookup"><span data-stu-id="99b32-114">To upgrade SQLCLR Assemblies</span></span>  
  
1.  <span data-ttu-id="99b32-115">Iniciar o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="99b32-115">Start Command Prompt.</span></span>  
  
2.  <span data-ttu-id="99b32-116">Ao prompt de comando, altere seu diretório ao local onde DQSInstaller.exe está disponível.</span><span class="sxs-lookup"><span data-stu-id="99b32-116">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="99b32-117">Se você instalou a instância padrão do SQL Server, o arquivo DQSInstaller.exe estará disponível em C:\Arquivos de Programas\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span><span class="sxs-lookup"><span data-stu-id="99b32-117">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
3.  <span data-ttu-id="99b32-118">No prompt de comando, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="99b32-118">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgradedlls  
    ```  
  
4.  <span data-ttu-id="99b32-119">As outras etapas são iguais às etapas 2 a 6 na seção [Executar o DQSInstaller.exe na tela Iniciar, no menu Iniciar ou no Windows Explorer](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) em [Executar o DQSInstaller.exe para concluir a instalação do Data Quality Server](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="99b32-119">Rest of the steps are same as steps 2-6 in the [Run DQSInstaller.exe from Start Screen, Start Menu or Windows Explorer](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) section in [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b32-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="99b32-120">See Also</span></span>  
 <span data-ttu-id="99b32-121">[Instalar o Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="99b32-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="99b32-122">Atualize o esquema de bancos de dados DQS depois de instalar a atualização do SQL Server</span><span class="sxs-lookup"><span data-stu-id="99b32-122">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>](upgrade-dqs-databases-schema-after-installing-sql-server-update.md)  
  
  

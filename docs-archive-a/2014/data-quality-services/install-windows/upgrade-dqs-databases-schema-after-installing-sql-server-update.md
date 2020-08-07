---
title: Atualizar o esquema de bancos de dados DQS depois de instalar a atualização do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: c8f3fbae-02c4-464d-a35c-7108f48c58cb
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 80a1714ea250cf7cf5d34bc9d208a42a64284308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574922"
---
# <a name="upgrade-dqs-databases-schema-after-installing-sql-server-update"></a><span data-ttu-id="5d855-102">Atualize o esquema de bancos de dados DQS depois de instalar a atualização do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d855-102">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>
  <span data-ttu-id="5d855-103">Depois que instalar uma atualização do SQL Server (patch, hotfix ou atualização cumulativa) em uma instância do DQS previamente configurada, você poderá ter de atualizar o esquema de bancos de dados do DQS executando o arquivo DQSInstaller.exe com o parâmetro de linha de comando **upgrade** .</span><span class="sxs-lookup"><span data-stu-id="5d855-103">After you have installed a SQL Server update (patch, hotfix, or cumulative update) on a previously configured DQS instance, you might have to upgrade the DQS databases schema by running the DQSInstaller.exe file with the **upgrade** command line parameter.</span></span> <span data-ttu-id="5d855-104">Caso contrário, você poderá receber o erro a seguir ao tentar se conectar ao Servidor do Data Quality usando seu Cliente do Data Quality:</span><span class="sxs-lookup"><span data-stu-id="5d855-104">Otherwise, you might receive the following error while trying to connect to Data Quality Server using your Data Quality Client:</span></span>  
  
```  
An error occurred in the Microsoft .NET Framework while trying to load assembly id 65581.  
```  
  
 <span data-ttu-id="5d855-105">Atualizar esquema de bancos de dados do DQS não afeta seus dados existentes nos bancos de dados do DQS (bases de dados de conhecimento, projetos de qualidade de dados e resultados exportados no banco de dados DQS_STAGING_DATA).</span><span class="sxs-lookup"><span data-stu-id="5d855-105">Upgrading DQS databases schema does not impact your existing data in the DQS databases (knowledge bases, data quality projects, and exported results in the DQS_STAGING_DATA database).</span></span> <span data-ttu-id="5d855-106">No entanto, você deve fazer backup de seus bancos de dados do DQS antes de atualizar o esquema de bancos de dados do DQS para impedir qualquer perda de dados acidental durante a atualização do esquema.</span><span class="sxs-lookup"><span data-stu-id="5d855-106">However, you must back up your DQS databases before upgrading DQS databases schema to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="5d855-107">Para obter informações sobre como fazer backup de bancos de dados DQS, veja [Fazendo backup e restaurando banco de dados do DQS](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="5d855-107">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d855-108">A maioria das atualizações do SQL Server exigirá uma atualização para o esquema de bancos de dados do DQS.</span><span class="sxs-lookup"><span data-stu-id="5d855-108">Most of the SQL Server updates will require an upgrade to the DQS databases schema.</span></span> <span data-ttu-id="5d855-109">Para obter informações sobre as atualizações do SQL Server que exigirão uma atualização para o esquema de bancos de dados do DQS, veja o gráfico na etapa 1.A em [Atualizar DQS: instalando atualizações cumulativas ou patches de hotfix no Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span><span class="sxs-lookup"><span data-stu-id="5d855-109">For information about the SQL Server updates that will require an upgrade to the DQS databases schema, see the chart in step 1.A in [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5d855-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5d855-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="5d855-111">Você deve estar conectado como um membro do grupo Administradores no computador do [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d855-111">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="5d855-112">Sua conta de usuário do Windows deve ser um membro da função de servidor fixa sysadmin na instância do SQL Server em que o [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="5d855-112">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-dqs-databases-schema"></a><span data-ttu-id="5d855-113">Para atualizar o esquema de bancos de dados do DQS</span><span class="sxs-lookup"><span data-stu-id="5d855-113">To upgrade DQS databases schema</span></span>  
  
1.  <span data-ttu-id="5d855-114">(Recomendado) Faça backup de seus bancos de dados do DQS antes de continuar com a atualização de esquema.</span><span class="sxs-lookup"><span data-stu-id="5d855-114">(Recommended) Back up your DQS databases before you proceed with the schema upgrade.</span></span> <span data-ttu-id="5d855-115">Para obter informações sobre como fazer backup de bancos de dados DQS, veja [Fazendo backup e restaurando banco de dados do DQS](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="5d855-115">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="5d855-116">Iniciar o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="5d855-116">Start Command Prompt.</span></span>  
  
3.  <span data-ttu-id="5d855-117">Ao prompt de comando, altere seu diretório ao local onde DQSInstaller.exe está disponível.</span><span class="sxs-lookup"><span data-stu-id="5d855-117">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="5d855-118">Se você instalou a instância padrão do SQL Server, o arquivo DQSInstaller.exe estará disponível em C:\Arquivos de Programas\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span><span class="sxs-lookup"><span data-stu-id="5d855-118">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
4.  <span data-ttu-id="5d855-119">No prompt de comando, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="5d855-119">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgrade  
    ```  
  
5.  <span data-ttu-id="5d855-120">O instalador solicita que você faça backup dos bancos de dados do DQS antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5d855-120">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="5d855-121">Se você já tiver feito backup dos bancos de dados do DQS, digite `Y` ou `Yes` e pressione ENTER para continuar com a atualização.</span><span class="sxs-lookup"><span data-stu-id="5d855-121">If you have already backed up your DQS databases, type `Y` or `Yes` and press ENTER to continue with the upgrade.</span></span>  
  
6.  <span data-ttu-id="5d855-122">Uma mensagem de conclusão é exibida depois da atualização bem-sucedida do esquema de bancos de dados do DQS.</span><span class="sxs-lookup"><span data-stu-id="5d855-122">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5d855-123">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5d855-123">Next Steps</span></span>  
 <span data-ttu-id="5d855-124">Faça logon no Servidor do Data Quality de um aplicativo Cliente do Data Quality.</span><span class="sxs-lookup"><span data-stu-id="5d855-124">Log on to the upgraded Data Quality Server from a Data Quality Client application.</span></span>  
  
 <span data-ttu-id="5d855-125">Para obter mais informações sobre como atualizar esquema de bancos de dados do DQS depois de instalar atualizações do SQL Server e etapas de solução de problemas associadas, veja [Atualizar DQS: instalando atualizações cumulativas ou patches de hotfix no Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span><span class="sxs-lookup"><span data-stu-id="5d855-125">For more information about upgrading DQS databases schema after installing SQL Server updates and associated troubleshooting steps, see [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d855-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5d855-126">See Also</span></span>  
 <span data-ttu-id="5d855-127">[Instalar o Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="5d855-127">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="5d855-128">Atualizar assemblies SQLCLR após atualizar o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5d855-128">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>](upgrade-sqlclr-assemblies-after-net-framework-update.md)  
  
  

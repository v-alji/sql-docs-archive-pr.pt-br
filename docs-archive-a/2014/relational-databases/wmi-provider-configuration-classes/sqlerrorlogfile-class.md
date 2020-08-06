---
title: Classe sqllogsfile | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
ms.assetid: 2b83ae4a-c0d4-414c-b6e5-a41ec7c13159
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d73f97ebddd7a1d18c73a2cbce7fe79dafc17a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679225"
---
# <a name="sqlerrorlogfile-class"></a><span data-ttu-id="dd0c9-102">Classe SqlErrorLogFile</span><span class="sxs-lookup"><span data-stu-id="dd0c9-102">SqlErrorLogFile Class</span></span>
  <span data-ttu-id="dd0c9-103">Fornece propriedades para exibição de informações sobre um arquivo de log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd0c9-103">Provides properties for viewing information about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd0c9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd0c9-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogFile  
{  
   uint32ArchiveNumber;  
   stringInstanceName;  
   datetimeLastModified;  
   uint32LogFileSize;  
   stringName;  
  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="dd0c9-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="dd0c9-105">Properties</span></span>  
 <span data-ttu-id="dd0c9-106">A classe sqllogsfile define as propriedades a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-106">The SQLErrorLogFile class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd0c9-107">ArchiveNumber</span><span class="sxs-lookup"><span data-stu-id="dd0c9-107">ArchiveNumber</span></span>|<span data-ttu-id="dd0c9-108">Tipo de dados: `uint32`</span><span class="sxs-lookup"><span data-stu-id="dd0c9-108">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="dd0c9-109">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="dd0c9-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="dd0c9-110">O número do arquivo morto do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-110">The archive number for the log file.</span></span>|  
|<span data-ttu-id="dd0c9-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="dd0c9-111">InstanceName</span></span>|<span data-ttu-id="dd0c9-112">Tipo de dados: `string`</span><span class="sxs-lookup"><span data-stu-id="dd0c9-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="dd0c9-113">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="dd0c9-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="dd0c9-114">Qualificadores: Chave</span><span class="sxs-lookup"><span data-stu-id="dd0c9-114">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="dd0c9-115">O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] onde o arquivo de log reside.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="dd0c9-116">LastModified</span><span class="sxs-lookup"><span data-stu-id="dd0c9-116">LastModified</span></span>|<span data-ttu-id="dd0c9-117">Tipo de dados: `datetime`</span><span class="sxs-lookup"><span data-stu-id="dd0c9-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="dd0c9-118">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="dd0c9-118">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="dd0c9-119">A data da última modificação do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-119">The date that the log file was last modified.</span></span>|  
|<span data-ttu-id="dd0c9-120">LogFileSize</span><span class="sxs-lookup"><span data-stu-id="dd0c9-120">LogFileSize</span></span>|<span data-ttu-id="dd0c9-121">Tipo de dados: `uint32`</span><span class="sxs-lookup"><span data-stu-id="dd0c9-121">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="dd0c9-122">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="dd0c9-122">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="dd0c9-123">O tamanho do arquivo de log, em bytes.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-123">The log file size, in bytes.</span></span>|  
|<span data-ttu-id="dd0c9-124">Nome</span><span class="sxs-lookup"><span data-stu-id="dd0c9-124">Name</span></span>|<span data-ttu-id="dd0c9-125">Tipo de dados: `string`</span><span class="sxs-lookup"><span data-stu-id="dd0c9-125">Data type: `string`</span></span><br /><br /> <span data-ttu-id="dd0c9-126">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="dd0c9-126">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="dd0c9-127">Qualificadores: Chave</span><span class="sxs-lookup"><span data-stu-id="dd0c9-127">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="dd0c9-128">O nome do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-128">The name of the log file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd0c9-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd0c9-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd0c9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="dd0c9-130">MOF</span></span>|<span data-ttu-id="dd0c9-131">Sqlmgmprovider xpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="dd0c9-131">Sqlmgmprovider xpsp2up.mof</span></span>|  
|<span data-ttu-id="dd0c9-132">DLL</span><span class="sxs-lookup"><span data-stu-id="dd0c9-132">DLL</span></span>|<span data-ttu-id="dd0c9-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="dd0c9-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="dd0c9-134">Namespace</span><span class="sxs-lookup"><span data-stu-id="dd0c9-134">Namespace</span></span>|<span data-ttu-id="dd0c9-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="dd0c9-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd0c9-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dd0c9-136">Example</span></span>  
 <span data-ttu-id="dd0c9-137">O exemplo a seguir recupera informações sobre todos os arquivos de log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em uma instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd0c9-137">The following example retrieves information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dd0c9-138">Para executar o exemplo, substitua \<*Instance_Name*> pelo nome da instância, por exemplo, ' instance1 '.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-138">To run the example, replace \<*Instance_Name*> with the name of the instance, for example, 'Instance1'.</span></span>  
  
```  
on error resume next  
set strComputer = "."  
set objWMIService = GetObject("winmgmts:\\.\root\Microsoft\SqlServer\ComputerManagement10")  
set LogFiles = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogFile WHERE InstanceName = '<Instance_Name>'")  
  
For Each logFile in LogFiles  
  
WScript.Echo "Instance Name:  " & logFile.InstanceName & vbNewLine _  
    & "Log File Name:  " & logFile.Name & vbNewLine _  
    & "Archive Number: " & logFile.ArchiveNumber & vbNewLine _  
    & "Log File Size:  " & logFile.LogFileSize & " bytes" & vbNewLine _  
    & "Last Modified:  " & logFile.LastModified & vbNewLine _  
  
Next   
```  
  
## <a name="comments"></a><span data-ttu-id="dd0c9-139">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd0c9-139">Comments</span></span>  
 <span data-ttu-id="dd0c9-140">Quando *InstanceName* não for fornecido na instrução WQL, a consulta retornará informações para a instância padrão.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-140">When *InstanceName* is not provided in the WQL statement, the query will return information for the default instance.</span></span> <span data-ttu-id="dd0c9-141">Por exemplo, a instrução WQL a seguir retornará informações sobre todos os arquivos de log da instância padrão (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-141">For example, the following WQL statement will return information about all log files from the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogFile"  
```  
  
## <a name="security"></a><span data-ttu-id="dd0c9-142">Segurança</span><span class="sxs-lookup"><span data-stu-id="dd0c9-142">Security</span></span>  
 <span data-ttu-id="dd0c9-143">Para se conectar a um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo de log por meio do WMI, você deve ter as seguintes permissões nos computadores locais e remotos:</span><span class="sxs-lookup"><span data-stu-id="dd0c9-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="dd0c9-144">Acesso de leitura ao namespace WMI do **Root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="dd0c9-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="dd0c9-145">Por padrão, todos usuários têm acesso de leitura por meio da permissão Habilitar Conta.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd0c9-146">Para obter informações sobre como verificar as permissões de WMI, consulte a seção segurança do tópico [Exibir arquivos de log offline](../logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-146">For information about how to verify WMI permissions, see the Security section of the topic [View Offline Log Files](../logs/view-offline-log-files.md).</span></span>  
  
-   <span data-ttu-id="dd0c9-147">Permissão de leitura para a pasta que contém os logs de erros.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-147">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="dd0c9-148">Por padrão, os logs de erros estão localizados no caminho a seguir (em que \<*Drive> \* representa a unidade em que você instalou o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e \<*InstanceName*> é o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="dd0c9-148">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="dd0c9-149">\*\* \<Drive> : \Arquivos de Programas\microsoft SQL Server\MSSQL11\*\* **. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="dd0c9-149">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL11** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="dd0c9-150">Se você se conectar através de um firewall, verifique se uma exceção está definida no firewall para WMI em computadores de destino remotos.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-150">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="dd0c9-151">Para obter mais informações, consulte [conectando-se ao WMI remotamente a partir do Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-151">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd0c9-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd0c9-152">See Also</span></span>  
 <span data-ttu-id="dd0c9-153">[Classe SqlErrorLogEvent](sqlerrorlogevent-class.md) </span><span class="sxs-lookup"><span data-stu-id="dd0c9-153">[SqlErrorLogEvent Class](sqlerrorlogevent-class.md) </span></span>  
 [<span data-ttu-id="dd0c9-154">Exibir arquivos de log offline</span><span class="sxs-lookup"><span data-stu-id="dd0c9-154">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  

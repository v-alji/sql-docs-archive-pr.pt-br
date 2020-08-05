---
title: Classe SqlErrorLogEvent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SqlErrorLogEvent class
- SqlErrorLogFile class
ms.assetid: bde6c467-38d0-4766-a7af-d6c9d6302b07
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 358b6906e422be2984f2ebdbde636ad0b8376993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572964"
---
# <a name="sqlerrorlogevent-class"></a><span data-ttu-id="6eecb-102">Classe SqlErrorLogEvent</span><span class="sxs-lookup"><span data-stu-id="6eecb-102">SqlErrorLogEvent Class</span></span>
  <span data-ttu-id="6eecb-103">Fornece propriedades para exibir eventos em um arquivo de log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificado.</span><span class="sxs-lookup"><span data-stu-id="6eecb-103">Provides properties for viewing events in a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eecb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6eecb-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogEvent   
{  
   stringFileName;  
   stringInstanceName;  
   datetimeLogDate;  
   stringMessage;  
   stringProcessInfo;  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="6eecb-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="6eecb-105">Properties</span></span>  
 <span data-ttu-id="6eecb-106">A classe SQLErrorLogEvent define as propriedades a seguir.</span><span class="sxs-lookup"><span data-stu-id="6eecb-106">The SQLErrorLogEvent class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6eecb-107">FileName</span><span class="sxs-lookup"><span data-stu-id="6eecb-107">FileName</span></span>|<span data-ttu-id="6eecb-108">Tipo de dados: `string`</span><span class="sxs-lookup"><span data-stu-id="6eecb-108">Data type: `string`</span></span><br /><br /> <span data-ttu-id="6eecb-109">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="6eecb-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="6eecb-110">O nome do arquivo do log de erros.</span><span class="sxs-lookup"><span data-stu-id="6eecb-110">The name of the error log file.</span></span>|  
|<span data-ttu-id="6eecb-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="6eecb-111">InstanceName</span></span>|<span data-ttu-id="6eecb-112">Tipo de dados: `string`</span><span class="sxs-lookup"><span data-stu-id="6eecb-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="6eecb-113">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="6eecb-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="6eecb-114">Qualificadores: Chave</span><span class="sxs-lookup"><span data-stu-id="6eecb-114">Qualifiers: Key</span></span><br /><br /> <span data-ttu-id="6eecb-115">O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] onde o arquivo de log reside.</span><span class="sxs-lookup"><span data-stu-id="6eecb-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="6eecb-116">LogDate</span><span class="sxs-lookup"><span data-stu-id="6eecb-116">LogDate</span></span>|<span data-ttu-id="6eecb-117">Tipo de dados: `datetime`</span><span class="sxs-lookup"><span data-stu-id="6eecb-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="6eecb-118">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="6eecb-118">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="6eecb-119">Qualificadores: Chave</span><span class="sxs-lookup"><span data-stu-id="6eecb-119">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="6eecb-120">A data e a hora em que o evento foi gravado no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="6eecb-120">The date and time that the event was recorded in the log file.</span></span>|  
|<span data-ttu-id="6eecb-121">Mensagem</span><span class="sxs-lookup"><span data-stu-id="6eecb-121">Message</span></span>|<span data-ttu-id="6eecb-122">Tipo de dados: `string`</span><span class="sxs-lookup"><span data-stu-id="6eecb-122">Data type: `string`</span></span><br /><br /> <span data-ttu-id="6eecb-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="6eecb-123">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="6eecb-124">A mensagem do evento.</span><span class="sxs-lookup"><span data-stu-id="6eecb-124">The event message.</span></span>|  
|<span data-ttu-id="6eecb-125">ProcessInfo</span><span class="sxs-lookup"><span data-stu-id="6eecb-125">ProcessInfo</span></span>|<span data-ttu-id="6eecb-126">Tipo de dados: `string`</span><span class="sxs-lookup"><span data-stu-id="6eecb-126">Data type: `string`</span></span><br /><br /> <span data-ttu-id="6eecb-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="6eecb-127">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="6eecb-128">Informações sobre a SPID (ID do processo do servidor de origem) do evento.</span><span class="sxs-lookup"><span data-stu-id="6eecb-128">Information about the source server process ID (SPID) for the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eecb-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="6eecb-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6eecb-130">MOF</span><span class="sxs-lookup"><span data-stu-id="6eecb-130">MOF</span></span>|<span data-ttu-id="6eecb-131">Sqlmgmproviderxpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="6eecb-131">Sqlmgmproviderxpsp2up.mof</span></span>|  
|<span data-ttu-id="6eecb-132">DLL</span><span class="sxs-lookup"><span data-stu-id="6eecb-132">DLL</span></span>|<span data-ttu-id="6eecb-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="6eecb-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="6eecb-134">Namespace</span><span class="sxs-lookup"><span data-stu-id="6eecb-134">Namespace</span></span>|<span data-ttu-id="6eecb-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="6eecb-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6eecb-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6eecb-136">Example</span></span>  
 <span data-ttu-id="6eecb-137">O exemplo a seguir mostra como recuperar valores para todos os eventos registrados em um arquivo de log especificado.</span><span class="sxs-lookup"><span data-stu-id="6eecb-137">The following example shows how to retrieve values for all logged events in a specified log file.</span></span> <span data-ttu-id="6eecb-138">Para executar o exemplo, substitua \<*Instance_Name*> pelo nome da instância do, como [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ' instance1 ', e substitua ' file_name ' pelo nome do arquivo de log de erros, como ' cafiler. 1 '.</span><span class="sxs-lookup"><span data-stu-id="6eecb-138">To run the example, replace \<*Instance_Name*> with the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as 'Instance1', and replace 'File_Name' with the name of the error log file, such as 'ERRORLOG.1'.</span></span>  
  
```  
on error resume next  
strComputer = "."  
Set objWMIService = GetObject("winmgmts:" _  
    & "{impersonationLevel=impersonate}!\\" _  
    & strComputer & "\root\MICROSOFT\SqlServer\ComputerManagement10")  
set logEvents = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogEvent WHERE InstanceName = '<Instance_Name>' AND FileName = 'File_Name'")  
  
For Each logEvent in logEvents  
WScript.Echo "Instance Name: " & logEvent.InstanceName & vbNewLine _  
    & "Log Date: " & logEvent.LogDate & vbNewLine _  
    & "Log File Name: " & logEvent.FileName & vbNewLine _  
    & "Process Info: " & logEvent.ProcessInfo & vbNewLine _  
    & "Message: " & logEvent.Message & vbNewLine _  
  
Next  
```  
  
## <a name="comments"></a><span data-ttu-id="6eecb-139">Comentários</span><span class="sxs-lookup"><span data-stu-id="6eecb-139">Comments</span></span>  
 <span data-ttu-id="6eecb-140">Quando *InstanceName* ou *filename* não forem fornecidos na instrução WQL, a consulta retornará informações para a instância padrão e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo de log atual.</span><span class="sxs-lookup"><span data-stu-id="6eecb-140">When *InstanceName* or *FileName* are not provided in the WQL statement, the query will return information for the default instance and the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span> <span data-ttu-id="6eecb-141">Por exemplo, a instrução WQL a seguir retornará todos os eventos de log do arquivo de log atual (ERRORLOG) na instância padrão (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="6eecb-141">For example, the following WQL statement will return all log events from the current log file (ERRORLOG) on the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogEvent"  
```  
  
## <a name="security"></a><span data-ttu-id="6eecb-142">Segurança</span><span class="sxs-lookup"><span data-stu-id="6eecb-142">Security</span></span>  
 <span data-ttu-id="6eecb-143">Para se conectar a um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo de log por meio do WMI, você deve ter as seguintes permissões nos computadores locais e remotos:</span><span class="sxs-lookup"><span data-stu-id="6eecb-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="6eecb-144">Acesso de leitura ao namespace WMI do **Root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="6eecb-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="6eecb-145">Por padrão, todos usuários têm acesso de leitura por meio da permissão Habilitar Conta.</span><span class="sxs-lookup"><span data-stu-id="6eecb-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
-   <span data-ttu-id="6eecb-146">Permissão de leitura para a pasta que contém os logs de erros.</span><span class="sxs-lookup"><span data-stu-id="6eecb-146">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="6eecb-147">Por padrão, os logs de erros estão localizados no caminho a seguir (em que \<*Drive> \* representa a unidade em que você instalou o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e \<*InstanceName*> é o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="6eecb-147">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="6eecb-148">\*\* \<Drive> : \Arquivos de Programas\microsoft SQL Server\MSSQL12\*\* **. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="6eecb-148">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="6eecb-149">Se você se conectar através de um firewall, verifique se uma exceção está definida no firewall para WMI em computadores de destino remotos.</span><span class="sxs-lookup"><span data-stu-id="6eecb-149">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="6eecb-150">Para obter mais informações, consulte [conectando-se ao WMI remotamente a partir do Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="6eecb-150">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eecb-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6eecb-151">See Also</span></span>  
 <span data-ttu-id="6eecb-152">[Classe sqllogsfile](sqlerrorlogfile-class.md) </span><span class="sxs-lookup"><span data-stu-id="6eecb-152">[SqlErrorLogFile Class](sqlerrorlogfile-class.md) </span></span>  
 [<span data-ttu-id="6eecb-153">Exibir arquivos de log offline</span><span class="sxs-lookup"><span data-stu-id="6eecb-153">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  

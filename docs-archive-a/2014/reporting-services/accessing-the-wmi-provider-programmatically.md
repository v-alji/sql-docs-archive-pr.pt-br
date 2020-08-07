---
title: Acessando o provedor WMI de forma programática | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
ms.assetid: 67bd266b-1484-4863-8152-060a993420a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6546d046fcd176eb5cc5fd462ea9a8a31c25b803
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575670"
---
# <a name="accessing-the-wmi-provider-programmatically"></a><span data-ttu-id="8e0a6-102">Acessando o provedor WMI programaticamente</span><span class="sxs-lookup"><span data-stu-id="8e0a6-102">Accessing the WMI Provider Programmatically</span></span>
  <span data-ttu-id="8e0a6-103">Este tópico está em construção.</span><span class="sxs-lookup"><span data-stu-id="8e0a6-103">This topic is under construction.</span></span>  
  
## <a name="wmi-provider-overview"></a><span data-ttu-id="8e0a6-104">Visão geral do provedor WMI</span><span class="sxs-lookup"><span data-stu-id="8e0a6-104">WMI Provider Overview</span></span>  
 <span data-ttu-id="8e0a6-105">O namespace usado para obter informações sobre o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] nos exemplos de código mostrados neste tópico é o namespace **System.Management**, encontrado no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e0a6-105">The namespace used to obtain information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in the code samples shown in this topic is the **System.Management** namespace, found in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="8e0a6-106">O namespace **System.Management** oferece um conjunto de classes de código gerenciado pelas quais os aplicativos do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] podem acessar e manipular informações de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="8e0a6-106">The **System.Management** namespace provides a set of managed code classes through which [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] applications can access and manipulate management information.</span></span> <span data-ttu-id="8e0a6-107">Para obter mais informações sobre como usar as classes WMI do Reporting Services que usam o namespace **System.Management**, confira “Acessar informações de gerenciamento com System.Managment” no SDK do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e0a6-107">For more information on using the Reporting Services WMI classes using the **System.Management** namespace, see "Accessing Management Information with System.Managment" in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
## <a name="finding-a-report-server-instance"></a><span data-ttu-id="8e0a6-108">Localizando uma instância do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="8e0a6-108">Finding a Report Server Instance</span></span>  
 <span data-ttu-id="8e0a6-109">O modo preferido de localizar informações sobre as suas instalações de servidor de relatório é enumerar pela coleção de instâncias WMI.</span><span class="sxs-lookup"><span data-stu-id="8e0a6-109">The preferred way of finding information on your report server installations is to enumerate through the WMI instance collection.</span></span> <span data-ttu-id="8e0a6-110">O exemplo a seguir mostra como localizar propriedades em todas as instâncias do servidor de relatório criando uma coleção e fazendo um loop pela coleção para exibir as propriedades.</span><span class="sxs-lookup"><span data-stu-id="8e0a6-110">The example below shows how to find properties on every report server instance by creating a collection, and looping through the collection to display the properties.</span></span>  
  
```vb  
Imports System  
Imports System.Management  
Imports System.IO  
  
Module Module1  
    Sub Main()  
        Const WmiNamespace As String = "\\<ServerName>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10\Admin"  
        Const WmiRSClass As String = _  
           "\\<ServerName>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10\admin:MSReportServer_ConfigurationSetting"  
  
        Dim serverClass As ManagementClass  
        Dim scope As ManagementScope  
        scope = New ManagementScope(WmiNamespace)  
        'Connect to the Reporting Services namespace.  
        scope.Connect()  
  
        'Create the server class.  
        serverClass = New ManagementClass(WmiRSClass)  
        'Connect to the management object.  
        serverClass.Get()  
        If serverClass Is Nothing Then Throw New Exception("No class found")  
  
        'Loop through the instances of the server class.  
        Dim instances As ManagementObjectCollection = serverClass.GetInstances()  
        Dim instance As ManagementObject  
        For Each instance In instances  
            Console.Out.WriteLine("Instance Detected")  
            Dim instProps As PropertyDataCollection = instance.Properties  
            Dim prop As PropertyData  
            For Each prop In instProps  
                Dim name As String = prop.Name  
                Dim val As Object = prop.Value  
                Console.Out.Write("Property Name: " + name)  
                If val Is Nothing Then  
                    Console.Out.WriteLine("     Value: <null>")  
                Else  
                    Console.Out.WriteLine("     Value: " + val.ToString())  
                End If  
            Next  
        Next  
  
        Console.WriteLine("--- Press any key ---")  
        Console.ReadKey()  
  
    End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Management;  
using System.IO;  
[assembly: CLSCompliant(true)]  
  
class Class1  
{  
    [STAThread]  
    static void Main(string[] args)  
    {  
        const string WmiNamespace = @"\\<ServerName>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10\Admin";  
        const string WmiRSClass =  
          @"\\<ServerName>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10\admin:MSReportServer_ConfigurationSetting";  
        ManagementClass serverClass;  
        ManagementScope scope;  
        scope = new ManagementScope(WmiNamespace);  
  
        // Connect to the Reporting Services namespace.  
        scope.Connect();  
        // Create the server class.  
        serverClass = new ManagementClass(WmiRSClass);  
        // Connect to the management object.  
        serverClass.Get();  
        if (serverClass == null)  
            throw new Exception("No class found");  
  
        // Loop through the instances of the server class.  
        ManagementObjectCollection instances = serverClass.GetInstances();  
  
        foreach (ManagementObject instance in instances)  
        {  
            Console.Out.WriteLine("Instance Detected");  
            PropertyDataCollection instProps = instance.Properties;  
            foreach (PropertyData prop in instProps)  
            {  
                string name = prop.Name;  
                object val = prop.Value;  
                Console.Out.Write("Property Name: " + name);  
                if (val != null)  
                    Console.Out.WriteLine("     Value: " + val.ToString());  
                else  
                    Console.Out.WriteLine("     Value: <null>");  
            }  
        }  
        Console.WriteLine("\n--- Press any key ---");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e0a6-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e0a6-111">See Also</span></span>  
 <span data-ttu-id="8e0a6-112">[Acessar o provedor WMI de Reporting Services](tools/access-the-reporting-services-wmi-provider.md) </span><span class="sxs-lookup"><span data-stu-id="8e0a6-112">[Access the Reporting Services WMI Provider](tools/access-the-reporting-services-wmi-provider.md) </span></span>  
 [<span data-ttu-id="8e0a6-113">Arquivo de configuração RSReportServer</span><span class="sxs-lookup"><span data-stu-id="8e0a6-113">RSReportServer Configuration File</span></span>](report-server/rsreportserver-config-configuration-file.md)  
  
  

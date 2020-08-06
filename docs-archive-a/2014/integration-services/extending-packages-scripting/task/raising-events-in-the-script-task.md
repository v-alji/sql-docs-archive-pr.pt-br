---
title: Acionar eventos na tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- events [Integration Services], scripts
- warnings [Integration Services]
- SSIS events, scripts
- errors [Integration Services], events
- SSIS Script task, events
- Events property
- Script task [Integration Services], events
ms.assetid: 21ea07d1-e267-4fb1-a6cc-82c95a39beae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e20a276b91e434b6915cfb218eba17c07acd6544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680563"
---
# <a name="raising-events-in-the-script-task"></a><span data-ttu-id="24668-102">Gerando eventos na tarefa Script</span><span class="sxs-lookup"><span data-stu-id="24668-102">Raising Events in the Script Task</span></span>
  <span data-ttu-id="24668-103">Os eventos fornecem um modo de relatar erros, avisos e outras informações, como o progresso ou status da tarefa, ao pacote que os contém.</span><span class="sxs-lookup"><span data-stu-id="24668-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="24668-104">O pacote fornece manipuladores de eventos para gerenciar notificações de eventos.</span><span class="sxs-lookup"><span data-stu-id="24668-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="24668-105">A tarefa Script pode gerar eventos chamando métodos na propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> do objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="24668-105">The Script task can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="24668-106">Para obter mais informações sobre como pacotes [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] manipulam eventos, consulte [Manipuladores de Eventos do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="24668-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="24668-107">Os eventos podem ser registrados em qualquer provedor de log que esteja habilitado no pacote.</span><span class="sxs-lookup"><span data-stu-id="24668-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="24668-108">Provedores de logs armazenam informações sobre eventos em um repositório de dados.</span><span class="sxs-lookup"><span data-stu-id="24668-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="24668-109">A tarefa Script também pode usar o método <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> para registrar informações para um provedor de logs sem gerar um evento.</span><span class="sxs-lookup"><span data-stu-id="24668-109">The Script task can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="24668-110">Para obter mais informações sobre como usar o método <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>, consulte [Registro em log na tarefa Script](logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="24668-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method, see [Logging in the Script Task](logging-in-the-script-task.md).</span></span>  
  
 <span data-ttu-id="24668-111">Para gerar um evento, a tarefa Script chama um dos métodos expostos pela propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="24668-111">To raise an event, the Script task calls one of the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span> <span data-ttu-id="24668-112">A tabela a seguir lista os métodos expostos pela propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="24668-112">The following table lists the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span>  
  
|<span data-ttu-id="24668-113">Evento</span><span class="sxs-lookup"><span data-stu-id="24668-113">Event</span></span>|<span data-ttu-id="24668-114">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="24668-114">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>|<span data-ttu-id="24668-115">Gera um evento personalizado definido pelo usuário no pacote.</span><span class="sxs-lookup"><span data-stu-id="24668-115">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>|<span data-ttu-id="24668-116">Informa o pacote sobre uma condição de erro.</span><span class="sxs-lookup"><span data-stu-id="24668-116">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireInformation%2A>|<span data-ttu-id="24668-117">Fornece informações ao usuário.</span><span class="sxs-lookup"><span data-stu-id="24668-117">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A>|<span data-ttu-id="24668-118">Informa ao pacote sobre o progresso da tarefa.</span><span class="sxs-lookup"><span data-stu-id="24668-118">Informs the package of the progress of the task.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireQueryCancel%2A>|<span data-ttu-id="24668-119">Retorna um valor que indica se o pacote exige o fechamento prematuro da tarefa.</span><span class="sxs-lookup"><span data-stu-id="24668-119">Returns a value that indicates whether the package needs the task to shut down prematurely.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>|<span data-ttu-id="24668-120">Informa ao pacote que a tarefa está em um estado que garante a notificação do usuário, mas não é uma condição de erro.</span><span class="sxs-lookup"><span data-stu-id="24668-120">Informs the package that the task is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
## <a name="events-example"></a><span data-ttu-id="24668-121">Exemplo de eventos</span><span class="sxs-lookup"><span data-stu-id="24668-121">Events Example</span></span>  
 <span data-ttu-id="24668-122">O exemplo a seguir demonstra como gerar eventos dentro da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="24668-122">The following example demonstrates how to raise events from within the Script task.</span></span> <span data-ttu-id="24668-123">O exemplo usa uma função nativa de API do Windows para determinar se uma conexão de Internet está disponível.</span><span class="sxs-lookup"><span data-stu-id="24668-123">The example uses a native Windows API function to determine whether an Internet connection is available.</span></span> <span data-ttu-id="24668-124">Se nenhuma conexão estiver disponível, será gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="24668-124">If no connection is available, it raises an error.</span></span> <span data-ttu-id="24668-125">Se uma conexão de modem potencialmente volátil estiver em uso, o exemplo gerará um aviso.</span><span class="sxs-lookup"><span data-stu-id="24668-125">If a potentially volatile modem connection is in use, the example raises a warning.</span></span> <span data-ttu-id="24668-126">Caso contrário, ela retornará uma mensagem informativa de que uma conexão de Internet foi detectada.</span><span class="sxs-lookup"><span data-stu-id="24668-126">Otherwise, it returns an informational message that an Internet connection has been detected.</span></span>  
  
```vb  
Private Declare Function InternetGetConnectedState Lib "wininet" _  
    (ByRef dwFlags As Long, ByVal dwReserved As Long) As Long  
  
Private Enum ConnectedStates  
    LAN = &H2  
    Modem = &H1  
    Proxy = &H4  
    Offline = &H20  
    Configured = &H40  
    RasInstalled = &H10  
End Enum  
  
Public Sub Main()  
  
    Dim dwFlags As Long  
    Dim connectedState As Long  
    Dim fireAgain as Boolean  
  
    connectedState = InternetGetConnectedState(dwFlags, 0)  
  
    If connectedState <> 0 Then  
        If (dwFlags And ConnectedStates.Modem) = ConnectedStates.Modem Then  
            Dts.Events.FireWarning(0, "Script Task Example", _  
                "Volatile Internet connection detected.", String.Empty, 0)  
        Else  
            Dts.Events.FireInformation(0, "Script Task Example", _  
                "Internet connection detected.", String.Empty, 0, fireAgain)  
        End If  
    Else  
        ' If not connected to the Internet, raise an error.  
        Dts.Events.FireError(0, "Script Task Example", _  
            "Internet connection not available.", String.Empty, 0)  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
using System.Runtime.InteropServices;  
  
public class ScriptMain  
{  
  
[DllImport("wininet")]  
        private extern static long InternetGetConnectedState(ref long dwFlags, long dwReserved);  
  
        private enum ConnectedStates  
        {  
            LAN = 0x2,  
            Modem = 0x1,  
            Proxy = 0x4,  
            Offline = 0x20,  
            Configured = 0x40,  
            RasInstalled = 0x10  
        };  
  
        public void Main()  
        {  
            //  
            long dwFlags = 0;  
            long connectedState;  
            bool fireAgain = true;  
            int state;  
  
            connectedState = InternetGetConnectedState(ref dwFlags, 0);  
            state = (int)ConnectedStates.Modem;  
            if (connectedState != 0)  
            {  
                if ((dwFlags & state) == state)  
                {  
                    Dts.Events.FireWarning(0, "Script Task Example", "Volatile Internet connection detected.", String.Empty, 0);  
                }  
                else  
                {  
                    Dts.Events.FireInformation(0, "Script Task Example", "Internet connection detected.", String.Empty, 0, ref fireAgain);  
                }  
            }  
            else  
            {  
                // If not connected to the Internet, raise an error.  
                Dts.Events.FireError(0, "Script Task Example", "Internet connection not available.", String.Empty, 0);  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
```  
  
<span data-ttu-id="24668-127">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="24668-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="24668-128">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="24668-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="24668-129">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="24668-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="24668-130">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="24668-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24668-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24668-131">See Also</span></span>  
 <span data-ttu-id="24668-132">[Manipuladores de eventos do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="24668-132">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="24668-133">Adicionar um manipulador de eventos a um pacote</span><span class="sxs-lookup"><span data-stu-id="24668-133">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  

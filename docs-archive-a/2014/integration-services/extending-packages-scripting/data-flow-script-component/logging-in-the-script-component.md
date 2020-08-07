---
title: Registro em log no componente de Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], logging
ms.assetid: 17c19787-379e-43fe-9107-e36e17ecda53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c29dfffee6cacb39272aef07caa5539555cdd4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575211"
---
# <a name="logging-in-the-script-component"></a><span data-ttu-id="9ae41-102">Registrando o componente Script</span><span class="sxs-lookup"><span data-stu-id="9ae41-102">Logging in the Script Component</span></span>
  <span data-ttu-id="9ae41-103">O registro de pacotes do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] permite que você salve informações detalhadas sobre o progresso da execução, resultados e problemas, por meio do registro de eventos predefinidos ou mensagens definidas pelo usuário para análise posterior.</span><span class="sxs-lookup"><span data-stu-id="9ae41-103">Logging in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages lets you save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="9ae41-104">O componente Script pode usar a classe <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> método da `ScriptMain` para registrar dados definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9ae41-104">The Script component can use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class to log user-defined data.</span></span> <span data-ttu-id="9ae41-105">Se o registro em log estiver habilitado e o evento **ScriptComponentLogEntry** estiver selecionado para o registro em log na guia **Detalhes** da caixa de diálogo **Configurar Logs de SSIS**, uma única chamada ao método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> armazenará informações do evento em todos os provedores de logs configurados para a tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="9ae41-105">If logging is enabled, and the **ScriptComponentLogEntry** event is selected for logging on the **Details** tab of the **Configure SSIS Logs** dialog box, a single call to the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method stores the event information in all the log providers that have been configured for the data flow task.</span></span>  
  
 <span data-ttu-id="9ae41-106">Este é um exemplo simples de registro em log:</span><span class="sxs-lookup"><span data-stu-id="9ae41-106">Here is a simple example of logging:</span></span>  
  
 `Dim bt(0) As Byte`  
  
 `Me.Log("Test Log Event", _`  
  
 `0, _`  
  
 `bt)`  
  
> [!NOTE]  
>  <span data-ttu-id="9ae41-107">Embora seja possível executar o registro em log diretamente do componente Script, talvez você queira implementar eventos em vez de registrá-los.</span><span class="sxs-lookup"><span data-stu-id="9ae41-107">Although you can perform logging directly from your Script component, you may want to consider implementing events rather than logging.</span></span> <span data-ttu-id="9ae41-108">Ao usar eventos, você pode habilitar o registro de mensagens de evento e também responder ao evento com manipuladores de eventos padrão ou definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9ae41-108">When using events, not only can you enable the logging of event messages, but you can respond to the event with default or user-defined event handlers.</span></span>  
  
 <span data-ttu-id="9ae41-109">Para obter mais informações sobre registro em log, consulte [Log do SSIS &#40;Integration Services&#41;](../../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="9ae41-109">For more information about logging, see [Integration Services &#40;SSIS&#41; Logging](../../performance/integration-services-ssis-logging.md).</span></span>  
  
<span data-ttu-id="9ae41-110">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9ae41-110">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9ae41-111">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="9ae41-111">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9ae41-112">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="9ae41-112">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9ae41-113">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="9ae41-113">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae41-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9ae41-114">See Also</span></span>  
 [<span data-ttu-id="9ae41-115">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9ae41-115">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  

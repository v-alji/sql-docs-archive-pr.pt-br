---
title: Solução de problemas de conectividade do pacote de ferramentas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, troubleshooting
- SSIS packages, troubleshooting
- Integration Services, troubleshooting
- connectivity [Integration Services], troubleshooting
- errors [Integration Services], troubleshooting
- packages [Integration Services], troubleshooting
ms.assetid: 08a019f5-8ba7-4527-97c1-e9846d4022ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1baac9af5a30fdc0f5b15e8ac56eb5badacc0edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680553"
---
# <a name="troubleshooting-tools-package-connectivity"></a><span data-ttu-id="f2490-102">Solucionando problemas de conectividade de pacotes de ferramentas</span><span class="sxs-lookup"><span data-stu-id="f2490-102">Troubleshooting Tools Package Connectivity</span></span>
  <span data-ttu-id="f2490-103">O [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contém recursos e ferramentas que você pode usar para solucionar problemas de conectividade entre pacotes e fontes de dados das quais os pacotes extraem e carregam dados.</span><span class="sxs-lookup"><span data-stu-id="f2490-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes features and tools that you can use to troubleshoot connectivity between packages and the data sources from which packages extract and load data.</span></span>  
  
## <a name="troubleshooting-issues-with-external-data-providers"></a><span data-ttu-id="f2490-104">Solucionando problemas com provedores de dados externos</span><span class="sxs-lookup"><span data-stu-id="f2490-104">Troubleshooting Issues with External Data Providers</span></span>  
 <span data-ttu-id="f2490-105">Muitos pacotes falham durante as interações com os provedores de dados externos.</span><span class="sxs-lookup"><span data-stu-id="f2490-105">Many packages fail during interactions with external data providers.</span></span> <span data-ttu-id="f2490-106">Entretanto, as mensagens que esses provedores retornam ao [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] geralmente não fornecem informações suficientes para iniciar a solução de problemas da interação.</span><span class="sxs-lookup"><span data-stu-id="f2490-106">However, the messages that those providers return to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] frequently do not provide enough information to start troubleshooting the interaction.</span></span> <span data-ttu-id="f2490-107">Para direcionar a solução de problemas necessária, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui as mensagens de log que podem ser usadas para solucionar problemas de interação do pacote com as fontes de dados externas.</span><span class="sxs-lookup"><span data-stu-id="f2490-107">To address this troubleshooting need, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes logging messages that you can use to troubleshoot a package's interaction with external data sources.</span></span>  
  
-   <span data-ttu-id="f2490-108">**Habilitar os logs e selecionar o evento Diagnóstico do pacote para ver as mensagens de solução de problemas**.</span><span class="sxs-lookup"><span data-stu-id="f2490-108">**Enable logging and select the package's Diagnostic event to see the troubleshooting messages**.</span></span> <span data-ttu-id="f2490-109">Os seguintes componentes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] são capazes de gravar uma mensagem para o log antes e após cada chamada a um provedor de dados externos:</span><span class="sxs-lookup"><span data-stu-id="f2490-109">The following [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components are capable of writing a message to the log before and after every call to an external data provider:</span></span>  
  
    -   <span data-ttu-id="f2490-110">Gerenciador de conexões do OLE DB, origem e destino do OLE DB</span><span class="sxs-lookup"><span data-stu-id="f2490-110">OLE DB connection manager, OLE DB source, and OLE DB destination</span></span>  
  
    -   <span data-ttu-id="f2490-111">Gerenciador de conexões do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] e origem do ADO NET</span><span class="sxs-lookup"><span data-stu-id="f2490-111">[!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and ADO NET source</span></span>  
  
    -   <span data-ttu-id="f2490-112">Tarefa Executar SQL</span><span class="sxs-lookup"><span data-stu-id="f2490-112">Execute SQL task</span></span>  
  
    -   <span data-ttu-id="f2490-113">Transformações Pesquisa, Comando OLE DB e Dimensão de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="f2490-113">Lookup transformation, OLE DB Command transformation, and Slowly Changing Dimension transformation</span></span>  
  
     <span data-ttu-id="f2490-114">As mensagens de log incluem o nome do método que está sendo chamado.</span><span class="sxs-lookup"><span data-stu-id="f2490-114">The log messages include the name of the method being called.</span></span> <span data-ttu-id="f2490-115">Por exemplo, essas mensagens de log podem incluir o método `Open` de um objeto `Connection` do OLE DB ou o método `ExecuteNonQuery` de um objeto `Command`.</span><span class="sxs-lookup"><span data-stu-id="f2490-115">For example, these log messages might include the `Open` method of an OLE DB `Connection` object or the `ExecuteNonQuery` method of a `Command` object.</span></span> <span data-ttu-id="f2490-116">As mensagens têm o seguinte formato, em que '%1!s!'</span><span class="sxs-lookup"><span data-stu-id="f2490-116">The messages have the following format, where '%1!s!'</span></span> <span data-ttu-id="f2490-117">é um espaço reservado para as informações do método:</span><span class="sxs-lookup"><span data-stu-id="f2490-117">is a placeholder for the method information:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: '%1!s!'.  
    ExternalRequest_post: '%1!s!'. The external request has completed.  
    ```  
  
     <span data-ttu-id="f2490-118">Para solucionar o problema de interação com o provedor de dados externos, analise o log para ver se cada mensagem "antes de" (`ExternalRequest_pre`) apresenta uma mensagem "depois de" (`ExternalRequest_post`) correspondente.</span><span class="sxs-lookup"><span data-stu-id="f2490-118">To troubleshoot the interaction with the external data provider, review the log to see whether every "before" message (`ExternalRequest_pre`) has a corresponding "after" message (`ExternalRequest_post`).</span></span> <span data-ttu-id="f2490-119">Caso não haja uma mensagem "depois de" correspondente, significa que o provedor de dados externos não respondeu conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="f2490-119">If there is no corresponding "after" message, you know that the external data provider did not respond as expected.</span></span>  
  
     <span data-ttu-id="f2490-120">O exemplo a seguir mostra algumas linhas de um log de exemplo que contém essas mensagens de log:</span><span class="sxs-lookup"><span data-stu-id="f2490-120">The following example shows some sample rows from a log that contains these logging messages:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: 'ITransactionJoin::JoinTransaction'.  
    ExternalRequest_post: 'ITransactionJoin::JoinTransaction succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Open'.  
    ExternalRequest_post: 'IDbConnection.Open succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.CreateCommand'.  
    ExternalRequest_post: 'IDbConnection.CreateCommand finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbCommand.ExecuteReader'.  
    ExternalRequest_post: 'IDbCommand.ExecuteReader finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.GetSchemaTable'.  
    ExternalRequest_post: 'IDataReader.GetSchemaTable finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.Close'.  
    ExternalRequest_post: 'IDataReader.Close finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Close'.  
    ExternalRequest_post: 'IDbConnection.Close finished'. The external request has completed."  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f2490-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f2490-121">See Also</span></span>  
 <span data-ttu-id="f2490-122">[Solucionando problemas de ferramentas para desenvolvimento de pacotes](troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="f2490-122">[Troubleshooting Tools for Package Development](troubleshooting-tools-for-package-development.md) </span></span>  
 [<span data-ttu-id="f2490-123">Ferramentas de solução de problemas de execução de pacote</span><span class="sxs-lookup"><span data-stu-id="f2490-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  

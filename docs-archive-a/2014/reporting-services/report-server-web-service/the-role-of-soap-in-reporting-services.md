---
title: A função do SOAP no Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- SOAP [Reporting Services], role in Reporting Services
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: f229c3ef-f2ca-448f-98f1-b8df350b9992
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05445eb1c95c5761595944867b6d0c20a6f1a412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680824"
---
# <a name="the-role-of-soap-in-reporting-services"></a><span data-ttu-id="46396-102">The Role of SOAP in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="46396-102">The Role of SOAP in Reporting Services</span></span>
  <span data-ttu-id="46396-103">O serviço Web do servidor de relatório usa o sistema de mensagens SOAP (Simple Object Access Protocol) para enviar comandos baseados em texto por meio de uma rede.</span><span class="sxs-lookup"><span data-stu-id="46396-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) messaging to send text-based commands over a network.</span></span> <span data-ttu-id="46396-104">Esses comandos assumem a forma de texto XML que é enviado por meio da Web usando HTTP.</span><span class="sxs-lookup"><span data-stu-id="46396-104">These commands take the form of XML text that is sent over the World Wide Web using HTTP.</span></span> <span data-ttu-id="46396-105">Usando o SOAP como seu protocolo de comunicação, o serviço Web do servidor de relatório permite aplicativos e componentes para trocar dados com o servidor de relatório usando uma infraestrutura largamente aceita e aberta.</span><span class="sxs-lookup"><span data-stu-id="46396-105">By using SOAP as its communication protocol, the Report Server Web service allows applications and components to exchange data with the report server using an open and widely accepted infrastructure.</span></span> <span data-ttu-id="46396-106">O padrão de SOAP é definido em www.w3.org/TR/SOAP.</span><span class="sxs-lookup"><span data-stu-id="46396-106">The SOAP standard is defined at www.w3.org/TR/SOAP.</span></span>  
  
 <span data-ttu-id="46396-107">Qualquer aplicativo cliente pode agir como um cliente de SOAP desde que seja o SOAP-atento e pode enviar solicitações de SOAP.</span><span class="sxs-lookup"><span data-stu-id="46396-107">Any client application can act as a SOAP client as long as it is SOAP-aware and can send SOAP requests.</span></span> <span data-ttu-id="46396-108">O Gerenciador de Relatórios é um cliente de SOAP.</span><span class="sxs-lookup"><span data-stu-id="46396-108">Report Manager is one such SOAP client.</span></span> <span data-ttu-id="46396-109">Ele fornece uma interface para o banco de dados do servidor de relatório em que todos os relatórios e conteúdo relacionado a relatório são armazenados.</span><span class="sxs-lookup"><span data-stu-id="46396-109">It provides an interface to the report server database in which all reports and report-related content is stored.</span></span> <span data-ttu-id="46396-110">Os usuários finais podem usar o aplicativo para navegar bem como gerenciar relatórios e pastas no namespace de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="46396-110">End users can use the application to browse through and manage reports and folders in the report server namespace.</span></span> <span data-ttu-id="46396-111">O Gerenciador de Relatórios é criado na infraestrutura de serviço Web do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="46396-111">Report Manager is built on the Report Server Web service infrastructure.</span></span>  
  
 <span data-ttu-id="46396-112">Um servidor de relatório age como um servidor de SOAP, um serviço do SOAP-atento que pode aceitar solicitações de clientes de SOAP e criar respostas apropriadas.</span><span class="sxs-lookup"><span data-stu-id="46396-112">A report server acts as a SOAP server, a SOAP-aware service that can accept requests from SOAP clients and create appropriate responses.</span></span> <span data-ttu-id="46396-113">O servidor trata as solicitações e envia respostas codificadas novamente para o cliente.</span><span class="sxs-lookup"><span data-stu-id="46396-113">The server handles the requests and sends encoded responses back to the client.</span></span>  
  
 <span data-ttu-id="46396-114">As mensagens de SOAP no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] assumem muitas formas diferentes, dependendo do tipo de solicitação feita pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="46396-114">SOAP messages in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] take many different forms, depending on the type of request made by the client.</span></span> <span data-ttu-id="46396-115">O exemplo a seguir representa uma solicitação de cliente de SOAP simples para remover um item do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="46396-115">The following example represents a simple SOAP client request to remove an item from the report server database.</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItem xmlns="https://www.microsoft.com/sql/ReportingServer">  
            <item>/Samples/Report1</item>  
        </DeleteItem>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="46396-116">O SOAP em si requer que as mensagens sejam colocadas em um elemento `Envelope`, com o tamanho da mensagem em um elemento `Body`.</span><span class="sxs-lookup"><span data-stu-id="46396-116">The SOAP itself requires that messages be put into an `Envelope` element, with the bulk of the message inside a `Body` element.</span></span> <span data-ttu-id="46396-117">Nesse exemplo, o corpo contém uma chamada para o método <xref:ReportService2010.ReportingService2010.DeleteItem%2A>, que assume um parâmetro de cadeia de caracteres representando o caminho do item a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="46396-117">In this example, the body contains a call to the <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method, which takes a string parameter representing the path of the item to delete.</span></span> <span data-ttu-id="46396-118">Você pode criar uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classe de proxy de cliente que encapsula todas as operações SOAP em métodos.</span><span class="sxs-lookup"><span data-stu-id="46396-118">You can create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] client proxy class that encapsulates all SOAP operations into methods.</span></span> <span data-ttu-id="46396-119">O método a seguir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] representa o exemplo de SOAP fornecido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="46396-119">The following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] method represents the SOAP example given earlier.</span></span>  
  
```  
public void DeleteItem(string item);  
```  
  
 <span data-ttu-id="46396-120">A resposta do servidor pode se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="46396-120">The response from the server might look like the following:</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItemResponse xmlns="https://www.microsoft.com/sql/ReportingServer" />  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="46396-121">O método <xref:ReportService2010.ReportingService2010.DeleteItem%2A> não tem nenhum valor de retorno, portanto, uma resposta vazia é retornada.</span><span class="sxs-lookup"><span data-stu-id="46396-121">The <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method has no return value, so an empty response is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46396-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46396-122">See Also</span></span>  
 <span data-ttu-id="46396-123">[Acessando a API SOAP](accessing-the-soap-api.md) </span><span class="sxs-lookup"><span data-stu-id="46396-123">[Accessing the SOAP API](accessing-the-soap-api.md) </span></span>  
 <span data-ttu-id="46396-124">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="46396-124">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="46396-125">[Reporting Services servidor de relatório](../reporting-services-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="46396-125">[Reporting Services Report Server](../reporting-services-report-server.md) </span></span>  
 [<span data-ttu-id="46396-126">Serviço Web do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="46396-126">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  

---
title: Implementando uma classe DataReader para uma extensão de processamento de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], data readers
- data readers [Reporting Services]
- DataReader class
- read-only data
ms.assetid: 23e286e7-6074-4fbe-be29-203420d6c3d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c9e55741c72d624b7149435ced90550135d8b4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685442"
---
# <a name="implementing-a-datareader-class-for-a-data-processing-extension"></a><span data-ttu-id="0e049-102">Implementando uma classe DataReader para uma extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="0e049-102">Implementing a DataReader Class for a Data Processing Extension</span></span>
  <span data-ttu-id="0e049-103">O objeto **DataReader** permite que um cliente recupere um fluxo de dados somente leitura, somente encaminhamento de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0e049-103">The **DataReader** object enables a client to retrieve a read-only, forward-only stream of data from a data source.</span></span> <span data-ttu-id="0e049-104">Os resultados são retornados à medida que a consulta é executada e são armazenados no buffer de rede no cliente até que você solicite-os usando o método **Read** da classe **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="0e049-104">Results are returned as the query executes and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader** class.</span></span> <span data-ttu-id="0e049-105">Para criar uma classe **DataReader**, implemente <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> e, opcionalmente, implemente <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span><span class="sxs-lookup"><span data-stu-id="0e049-105">To create a **DataReader** class, implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> and optionally implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span></span> <span data-ttu-id="0e049-106">O uso de um objeto **DataReader** aumenta o desempenho do aplicativo recuperando dados assim que eles estão disponíveis, em vez de aguardar que todos os resultados da consulta sejam retornados e (por padrão) armazenando somente uma linha por vez na memória, reduzindo a sobrecarga do sistema.</span><span class="sxs-lookup"><span data-stu-id="0e049-106">Using a **DataReader** object increases application performance both by retrieving data as soon as it is available, rather than waiting for the entire results of the query to be returned, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="0e049-107">Depois de criar uma instância da classe **Command**, você cria um objeto **DataReader** chamando **Command.ExecuteReader** para recuperar linhas da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0e049-107">After creating an instance of your **Command** class, you create a **DataReader** object by calling **Command.ExecuteReader** to retrieve rows from the data source.</span></span> <span data-ttu-id="0e049-108">A implementação de **DataReader** deve fornecer duas funcionalidades básicas: acesso somente encaminhamento aos conjuntos de resultados obtidos pela execução de um comando e acesso aos tipos de coluna, nomes e valores de cada linha.</span><span class="sxs-lookup"><span data-stu-id="0e049-108">The **DataReader** implementation must provide two basic capabilities: forward-only access over the result sets obtained by executing a command and access to the column types, names, and values within each row.</span></span> <span data-ttu-id="0e049-109">Os clientes usam o método **Read** do objeto **DataReader** para obter uma linha dos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="0e049-109">Clients use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span>  
  
 <span data-ttu-id="0e049-110">No Designer de Relatórios, o objeto **DataReader** é usado para recuperar uma lista de campos, além de informações de esquema sobre o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0e049-110">In Report Designer, your **DataReader** object is used to retrieve a list of fields as well as schema information about the result set.</span></span> <span data-ttu-id="0e049-111">Isso é realizado pela implementação dos métodos **GetName**, **GetValue**, **GetFieldType** e **GetOrdinal** da interface <xref:Microsoft.ReportingServices.DataProcessing.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="0e049-111">This is accomplished by implementing the **GetName**, **GetValue**, **GetFieldType,** and **GetOrdinal** methods of the <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> interface.</span></span>  
  
 <span data-ttu-id="0e049-112">A interface de <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> permite que você ofereça informações específicas de agregação sobre o seu conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0e049-112">The <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> interface allows you to supply specific aggregation information about your result set.</span></span> <span data-ttu-id="0e049-113">Para obter uma implementação de exemplo da classe **DataReader**, consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="0e049-113">For a sample **DataReader** class implementation, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e049-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e049-114">See Also</span></span>  
 <span data-ttu-id="0e049-115">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="0e049-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="0e049-116">[Implementando uma extensão de processamento de dados](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="0e049-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="0e049-117">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="0e049-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  

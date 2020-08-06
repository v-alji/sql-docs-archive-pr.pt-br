---
title: Exemplo de fluxo de trabalho personalizado (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: dfd1616c-a75c-4f32-bdb1-7569e367bf41
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ee9d6e18bf4e54ae5eb6af6a56494fff0db28684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678819"
---
# <a name="custom-workflow-example-master-data-services"></a><span data-ttu-id="c1394-102">Exemplo de fluxo de trabalho personalizado (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c1394-102">Custom Workflow Example (Master Data Services)</span></span>
  <span data-ttu-id="c1394-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] , ao criar uma biblioteca de classes de fluxo de trabalho personalizada, você cria uma classe que implementa a interface [Microsoft. MasterDataServices. WorkflowTypeExtender. IWorkflowTypeExtender](/previous-versions/sql/sql-server-2016/hh758785(v=sql.130)) .</span><span class="sxs-lookup"><span data-stu-id="c1394-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)], when you create a custom workflow class library, you create a class that implements the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender](/previous-versions/sql/sql-server-2016/hh758785(v=sql.130)) interface.</span></span> <span data-ttu-id="c1394-104">Essa interface inclui um método, [Microsoft. MasterDataServices. WorkflowTypeExtender. IWorkflowTypeExtender. StartWorkflow \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)), que é chamado por SQL Server serviço de integração de fluxo de trabalho do MDS quando um fluxo de trabalho é iniciado.</span><span class="sxs-lookup"><span data-stu-id="c1394-104">This interface includes one method, [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)), that is called by SQL Server MDS Workflow Integration Service when a workflow starts.</span></span> <span data-ttu-id="c1394-105">O método [Microsoft. MasterDataServices. WorkflowTypeExtender. IWorkflowTypeExtender. StartWorkflow \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) contém dois parâmetros: *WorkflowType* contém o texto que você inseriu na caixa de texto **tipo de fluxo de trabalho** em [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] e *dataelement* contém metadados e dados de item para o item que disparou a regra de negócio de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c1394-105">The [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method contains two parameters: *workflowType* contains the text you entered in the **Workflow type** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], and *dataElement* contains metadata and item data for the item that triggered the workflow business rule.</span></span>  
  
## <a name="custom-workflow-example"></a><span data-ttu-id="c1394-106">Exemplo de fluxo de trabalho personalizado</span><span class="sxs-lookup"><span data-stu-id="c1394-106">Custom Workflow Example</span></span>  
 <span data-ttu-id="c1394-107">O exemplo de código a seguir mostra como implementar o método [Microsoft. MasterDataServices. WorkflowTypeExtender. IWorkflowTypeExtender. StartWorkflow \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) para extrair os atributos Name, Code e LastChgUserName dos dados XML para o elemento que disparou a regra de negócio de fluxo de trabalho e como chamar um procedimento armazenado para inseri-los em outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c1394-107">The following code example shows how you how to implement the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method to extract the Name, Code, and LastChgUserName attributes from the XML data for the element that triggered the workflow business rule, and how to call a stored procedure to insert them into another database.</span></span> <span data-ttu-id="c1394-108">Para obter um exemplo do XML dos dados de item e uma explicação das marcas que ele contém, consulte [Descrição de XML de fluxo de trabalho personalizado &#40;Master Data Services&#41;](create-a-custom-workflow-xml-description.md).</span><span class="sxs-lookup"><span data-stu-id="c1394-108">For an example of the item data XML and an explanation of the tags it contains, see [Custom Workflow XML Description &#40;Master Data Services&#41;](create-a-custom-workflow-xml-description.md).</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Data.SqlClient;  
using System.Xml;  
  
using Microsoft.MasterDataServices.Core.Workflow;  
  
namespace MDSWorkflowTestLib  
{  
    public class WorkflowTester : IWorkflowTypeExtender  
    {  
        #region IWorkflowTypeExtender Members  
  
        public void StartWorkflow(string workflowType, System.Xml.XmlElement dataElement)  
        {  
            // Extract the attributes we want out of the element data.  
            XmlNode NameNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/Name");  
            XmlNode CodeNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/Code");  
            XmlNode EnteringUserNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/LastChgUserName");  
  
            // Open a connection on the workflow database.  
            SqlConnection workflowConn = new SqlConnection(@"Data Source=<Server instance>; Initial Catalog=WorkflowTest; Integrated Security=True");  
  
            // Create a command to call the stored procedure that adds a new user to the workflow database.  
            SqlCommand addCustomerCommand = new SqlCommand("AddNewCustomer", workflowConn);  
            addCustomerCommand.CommandType = System.Data.CommandType.StoredProcedure;  
            addCustomerCommand.Parameters.Add(new SqlParameter("@Name", NameNode.InnerText));  
            addCustomerCommand.Parameters.Add(new SqlParameter("@Code", CodeNode.InnerText));  
            addCustomerCommand.Parameters.Add(new SqlParameter("@EnteringUser", EnteringUserNode.InnerText));  
  
            // Execute the command.  
            workflowConn.Open();  
            addCustomerCommand.ExecuteNonQuery();  
            workflowConn.Close();  
        }  
  
        #endregion  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1394-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c1394-109">See Also</span></span>  
 [<span data-ttu-id="c1394-110">Criar um fluxo de trabalho personalizado &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c1394-110">Create a Custom Workflow &#40;Master Data Services&#41;</span></span>](create-a-custom-workflow-master-data-services.md)  
  
  

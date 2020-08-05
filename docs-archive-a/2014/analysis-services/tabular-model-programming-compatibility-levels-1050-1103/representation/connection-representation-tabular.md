---
title: Representação de conexão (tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 4b410b16-d36e-4185-bb20-922e66e5e2b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 60f3fdc10baf5dc3be9cd1b0ee6196d2a8da3d2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572235"
---
# <a name="connection-representation-tabular"></a><span data-ttu-id="93723-102">Representação de conexão (de tabela)</span><span class="sxs-lookup"><span data-stu-id="93723-102">Connection Representation (Tabular)</span></span>
  <span data-ttu-id="93723-103">O objeto de conexão define a origem dos dados que populam o modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="93723-103">The connection object defines the source of the data that populates the tabular model.</span></span>  
  
## <a name="connection-representation"></a><span data-ttu-id="93723-104">Representação de conexão</span><span class="sxs-lookup"><span data-stu-id="93723-104">Connection Representation</span></span>  
 <span data-ttu-id="93723-105">A especificação do objeto de conexão segue as regras de provedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="93723-105">The specification for the connection object follows the rules of OLE DB providers.</span></span>  
  
### <a name="connection-in-amo"></a><span data-ttu-id="93723-106">Conexão em AMO</span><span class="sxs-lookup"><span data-stu-id="93723-106">Connection in AMO</span></span>  
 <span data-ttu-id="93723-107">Ao usar o AMO para gerenciar um banco de dados modelo de tabela, o objeto <xref:Microsoft.AnalysisServices.DataSource> no AMO coincide um-para-um ao objeto lógico de conexão.</span><span class="sxs-lookup"><span data-stu-id="93723-107">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.DataSource> object in AMO matches one-to-one to the connection logical object.</span></span>  
  
 <span data-ttu-id="93723-108">O snippet de código a seguir mostra como criar uma fonte de dados de AMO ou objeto de conexão em um modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="93723-108">The following code snippet shows how to create an AMO data source, or Connection object in a tabular model.</span></span>  
  
```  
  
//Create an OLEDB connection string  
StringBuilder SqlCnxStr = new StringBuilder();  
SqlCnxStr.Append(String.Format("Data Source={0};" ,SQLServer.Text));  
SqlCnxStr.Append(String.Format("Initial Catalog={0};", SQLDatabase.Text));  
SqlCnxStr.Append(String.Format("Persist Security Info={0};", false));  
SqlCnxStr.Append(String.Format("Integrated Security={0};", "SSPI"));  
SqlCnxStr.Append(String.Format("Provider={0}", "SQLNCLI11"));  
String DatasourceCnxString = SqlCnxStr.ToString();  
  
//Verify connection string and connectivity  
System.Data.OleDb.OleDbConnection OleDbCnx = new System.Data.OleDb.OleDbConnection(DatasourceCnxString);  
try  
{  
    OleDbCnx.Open();  
}  
catch ()  
{  
    throw;  
}  
String newDataSourceName = (string.IsNullOrEmpty(DataSourceName.Text) || string.IsNullOrWhiteSpace(DataSourceName.Text)) ? SQLDatabase.Text : DataSourceName.Text;  
AMO.DataSource newDatasource = newDatabase.DataSources.Add(newDataSourceName, newDataSourceName);  
newDatasource.ConnectionString = DatasourceCnxString.Text;  
if (impersonateServiceAccount.Checked)  
    newDatasource.ImpersonationInfo = new AMO.ImpersonationInfo(AMO.ImpersonationMode.ImpersonateServiceAccount);  
else  
{  
    if (String.IsNullOrEmpty(impersonateAccountUserName.Text))  
    {  
        MessageBox.Show(String.Format("Account User Name cannot be blank when using 'ImpersonateAccount' mode"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
        return;  
    }  
    newDatasource.ImpersonationInfo = new AMO.ImpersonationInfo(AMO.ImpersonationMode.ImpersonateAccount, impersonateAccountUserName.Text, impersonateAccountPassword.Text);  
}  
newDatasource.Update();  
  
```  
  
## <a name="tabular-amo-2012-sample"></a><span data-ttu-id="93723-109">Exemplo de Tabular AMO 2012</span><span class="sxs-lookup"><span data-stu-id="93723-109">Tabular AMO 2012 sample</span></span>  
 <span data-ttu-id="93723-110">Para compreender melhor como usar o AMO para criar e manipular representações de conexão, consulte o código-fonte do exemplo Tabular AMO 2012; verifique especificamente o seguinte arquivo de origem: Database.cs.</span><span class="sxs-lookup"><span data-stu-id="93723-110">To have a better understanding on how to use AMO to create and manipulate connection representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="93723-111">O exemplo está disponível no Codeplex.</span><span class="sxs-lookup"><span data-stu-id="93723-111">The sample is available at Codeplex.</span></span> <span data-ttu-id="93723-112">O código de exemplo é fornecido apenas como um suporte aos conceitos lógicos explicados aqui e não deve ser usado em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="93723-112">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  

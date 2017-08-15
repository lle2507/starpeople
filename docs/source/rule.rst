General Rules
=============

Phần này mô tả các quy định theo chuẩn RESTful, các biến và giá trị mặc định cần thiết.

.. _in-rule-res-header:

Response header
---------------
Response header phải là kiểu JSON::

    {"integer":1, "boolean":true, "string":"^_^"}

.. _in-rule-res-status:

Response status
---------------
Trong JSON object trả về luôn có key status quy định trạng thái xử lý của Server.
Là một biến kiểu ``boolean`` với hai trạng thái:

* true - Server hoàn thành việc xử lý.
* false - Server hoàn thành việc xử lý kèm cảnh báo.

Nếu ``false`` thì thiết bị sẽ tìm thêm key ``message`` để xác định tình trạng:

.. code-block:: restructuredtext

    # True
    .. response:: 
        :status: true

    # False
    .. response:: 
        :status: false
        :message: Something wrong ;((

.. _in-rule-kind-mapping:

Kind definition
---------------
Là một biến kiểu ``integer`` xác định loại phép.

* 0 - Nghỉ phép năm.
* 1 - Nghỉ thai sản.
* 2 - Nghỉ phép không lương.

.. _in-rule-approval-mapping:

Approval definition
-------------------
Là một biến kiểu ``integer`` xác định trạng thái duyệt đơn nghỉ phép, tăng ca.

* 0 - Không duyệt.
* 1 - Đồng ý.
* 2 - Yêu cầu chỉnh sửa.

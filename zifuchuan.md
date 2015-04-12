/// <summary>
+    /// 使窗口的中的指定控件支持运行时移动
+    /// TODO:运行时缩放
+    /// </summary>
+    public class ControlMoveResize
+    {
+        #region 私有成员
+        bool IsMoving = false;
+        Point pCtrlLastCoordinate = new Point(0,0);
+        Point pCursorOffset = new Point(0, 0);
+        Point pCursorLastCoordinate = new Point(0, 0);
+        private Control ctrl = null;
+        private ScrollableControl Containe = null;
+        #endregion
+        #region 私有方法
+        /// <summary>
+        /// 在鼠标左键按下的状态记录鼠标当前的位置,以及被移动组件的当前位置
+        /// </summary>
+        /// <param name="sender"></param>
+        /// <param name="e"></param>
+        private void MouseDown(object sender, MouseEventArgs e)
+        {
+            if (Containe == null)
+            {
+                return;
+            }
+            if (e.Button == MouseButtons.Left)
+            {
+                IsMoving = true;
+                pCtrlLastCoordinate.X = ctrl.Left;
+                pCtrlLastCoordinate.Y = ctrl.Top;
+                pCursorLastCoordinate.X = Cursor.Position.X;
+                pCursorLastCoordinate.Y = Cursor.Position.Y;
+            }
+        }
+        private void MouseMove(object sender, MouseEventArgs e)
+        {
+            if (Containe == null)
+            {
+                return;
+            }
+              
+            if (e.Button == MouseButtons.Left)
+            {
+                if (this.IsMoving)
+                {
+                    Point pCursor = new Point(Cursor.Position.X, Cursor.Position.Y);
+                  
+                    pCursorOffset.X = pCursor.X - pCursorLastCoordinate.X;
+               
+                    pCursorOffset.Y = pCursor.Y - pCursorLastCoordinate.Y;
+                    ctrl.Left = pCtrlLastCoordinate.X + pCursorOffset.X;
+                    ctrl.Top = pCtrlLastCoordinate.Y + pCursorOffset.Y;
+                }
+
+            }
+        }
+ 
+        private void MouseUp(object sender, MouseEventArgs e)
+        {
+            if (Containe == null)
+            {
+                return;
+            }
+            if (this.IsMoving)
+            if (e.Button == MouseButtons.Left)
+            {
+                if (this.IsMoving)
+                {
+                    Point pCursor = new Point(Cursor.Position.X, Cursor.Position.Y);
+                  
+                    pCursorOffset.X = pCursor.X - pCursorLastCoordinate.X;
+               
+                    pCursorOffset.Y = pCursor.Y - pCursorLastCoordinate.Y;
+                    ctrl.Left = pCtrlLastCoordinate.X + pCursorOffset.X;
+                    ctrl.Top = pCtrlLastCoordinate.Y + pCursorOffset.Y;
+                }
+
+            }
+        }
+ 
+        private void MouseUp(object sender, MouseEventArgs e)
+        {
+            if (Containe == null)
+            {
+                return;
+            }
+            if (this.IsMoving)
+            {
+                if (pCursorOffset.X == 0 && pCursorOffset.Y == 0)
+                {
+                    return;
+                }
+                if ((pCtrlLastCoordinate.X + pCursorOffset.X + ctrl.Width) > 0)
+                {
+                    ctrl.Left = pCtrlLastCoordinate.X + pCursorOffset.X;
+                }
+                else
+                {
+                    ctrl.Left = 0;
+                }
+            {
+                if (pCursorOffset.X == 0 && pCursorOffset.Y == 0)
+                {
+                    return;
+                }
+                if ((pCtrlLastCoordinate.X + pCursorOffset.X + ctrl.Width) > 0)
+                {
+                    ctrl.Left = pCtrlLastCoordinate.X + pCursorOffset.X;
+                }
+                else
+                {
+                    ctrl.Left = 0;
+                }


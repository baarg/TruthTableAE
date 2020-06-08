import javax.swing.*;
import javax.swing.event.TableModelEvent;
import javax.swing.event.TableModelListener;
import javax.swing.table.DefaultTableModel;
import javax.swing.table.TableColumn;
import javax.swing.table.TableColumnModel;
import javax.swing.table.TableModel;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

class Scratch {
    public static void main(String[] args) {
        JFrame frame = new JFrame("table");
        frame.setSize(480,720);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(null);

        String[] data = new String[4];
        String column[][] = new String[4][4];
        DefaultTableModel tableModel = new DefaultTableModel(column,data);
        JTable table = new JTable(tableModel);
        JScrollPane scrollPane = new JScrollPane(table);
        scrollPane.setBounds(20,20,400,400);

        JButton button = new JButton("Ok");
        button.setBounds(20,500,100,20);

        JTextField textField = new JTextField();
        textField.setBounds(140,500,200,20);


        button.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent actionEvent) {
                int number = Integer.parseInt(textField.getText());
                int conum = tableModel.getColumnCount();
                int ronum = tableModel.getRowCount();

                for (int i = 0; i < (Math.pow(2, number)); i++) {
                    tableModel.addRow(new String[]{});
                }
                for (int i = 0; i < (number); i++) {
                    tableModel.addColumn("A");
                }
                tableModel.addColumn("F");

                for (int k =0; k<ronum;k++) {
                    tableModel.removeRow(0);
                }
                for (int k =0; k<conum;k++) {
                    TableColumn tcol = table.getColumnModel().getColumn(0);
                    table.removeColumn(tcol);
                }
                int n=1;
                for (int i=table.getColumnCount()-2; i>=0;i--){
                   int c=0,v=0;
                   int on = 0;
                    for (int j=1; j<=table.getRowCount();j++) {
                        table.setValueAt(on, j-1, i);
                        c++;
                        if (c == n) {
                            c = 0;
                            if(v==0) {
                                on = 1;
                                v = 1;
                            }
                            else {
                                on = 0;
                                v=0;
                            }
                        }
                    }
                    n*=2;
                }


            }


        });

        frame.add(scrollPane);
        frame.add(button);
        frame.add(textField);

        frame.setVisible(true);
    }
}

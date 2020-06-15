java file

package com.example.android.courtcounter;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    /**
     * points value*/
    int pointsA=0;
    int pointsB=0;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    /**
     * Displays the given score for Team A.
     */
    public void displayForTeamA(int score) {
        TextView scoreView = (TextView) findViewById(R.id.team_a_score);
        scoreView.setText(String.valueOf(score));
    }
    /**
     *  THREE POINTS FUNCTION*/
    public void threepointsA(View view){
        pointsA=pointsA+3;
        displayForTeamA(pointsA);
    }
    /**
     *  TWO POINTS FUNCTION*/
    public void twopointsA(View view){
        pointsA=pointsA+2;
        displayForTeamA(pointsA);
    }
    /**
     * FREE THROW FUNCTION*/
    public void freethrowA(View view){
        pointsA=pointsA+1;
        displayForTeamA(pointsA);
    }
    /**
     * function for foul points for team A
     */
    public void foulA(View view){
        displayForTeamA(--pointsA);
    }
    /**
     * reset function */

    public void reset(View view){
        pointsA = 0;
        pointsB = 0;
        displayForTeamB(pointsB);
        displayForTeamA(pointsA);
    }

    /**     * Displays the given score for Team B.
     */
    public void displayForTeamB(int score) {
        TextView scoreView = (TextView) findViewById(R.id.team_b_score);
        scoreView.setText(String.valueOf(score));
    }
    /**
     *  THREE POINTS FUNCTION*/
    public void threepointsB(View view){
        pointsB=pointsB+3;
        displayForTeamB(pointsB);
    }
    /**
     *  TWO POINTS FUNCTION*/
    public void twopointsB(View view){
        pointsB=pointsB+2;
        displayForTeamB(pointsB);
    }
    /**
     * FREE THROW FUNCTION*/
    public void freethrowB(View view){
        pointsB=pointsB+1;
        displayForTeamB(pointsB);
    }

    /**
     * function for foul points for team B
     */
    public void foulB(View view){
        displayForTeamB(--pointsB);
    }
}


xml file


<?xml version="1.0" encoding="utf-8"?><RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    >

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="horizontal">

        <LinearLayout
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:orientation="vertical"
            tools:context=".MainActivity">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_gravity="center"
                android:layout_marginTop="16sp"
                android:layout_marginBottom="24dp"
                android:fontFamily="sans-serif-medium"
                android:text="Team A"
                android:textColor="#616161"
                android:textSize="14sp" />

            <TextView
                android:id="@+id/team_a_score"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_gravity="cente
                android:fontFamily="sans-serif-light"
                android:text="0"
                android:textColor="#000000"
                android:textSize="56sp" />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="24dp"
                android:layout_marginTop="8dp"
                android:layout_marginRight="24dp"
                android:onClick="threepointsA"
                android:text="+3 POINTS" />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="24dp"
                android:layout_marginTop="8dp"
                android:layout_marginRight="24dp"
                android:onClick="twopointsA"
                android:text="+2 POINTS" />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="8dp"
                android:layout_marginLeft="24dp"
                android:layout_marginRight="24dp"
                android:onClick="freethrowA"
                android:text="FREE THROW" />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="24dp"
                android:layout_marginTop="8dp"
                android:layout_marginRight="24dp"
                android:onClick="foulA"
                android:text="FOUL" />

        </LinearLayout>

        <View
            android:layout_width="1dp"
            android:layout_height="350dp"
            android:layout_marginTop="16dp"
            android:background="@android:color/darker_gray" />

        <LinearLayout
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:orientation="vertical"
            tools:context=".MainActivity">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_gravity="center"
                android:layout_marginTop="16dp"
                android:layout_marginBottom="24dp"
                android:fontFamily="sans-serif-medium"
                android:text="Team B"
                android:textColor="#616161"
                android:textSize="14sp" />

            <TextView
                android:id="@+id/team_b_score"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_gravity="center"
                android:fontFamily="sans-serif-light"
                android:text="0"
                android:textColor="#000000"
                android:textSize="56sp" />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="24dp"
                android:layout_marginTop="8dp"
                android:layout_marginRight="24dp"
                android:onClick="threepointsB"
                android:text="+3 POINTS" />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="24dp"
                android:layout_marginTop="8dp"
                android:layout_marginRight="24dp"
                android:onClick="twopointsB"
                android:text="+2 POINTS" />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="24dp"
                android:layout_marginTop="8dp"
                android:layout_marginRight="24dp"
                android:onClick="freethrowB"
                android:text="FREE THROW" />

            <Button
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="24dp"
                android:layout_marginTop="8dp"
                android:layout_marginRight="24dp"
                android:onClick="foulB"
                android:text="FOUL" />

        </LinearLayout>

    </LinearLayout>

    <Button
        android:layout_marginBottom="32dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:onClick="reset"
        android:layout_alignParentBottom="true"
        android:layout_centerHorizontal="true"
        android:text="RESET" />
    
	</RelativeLayout>
